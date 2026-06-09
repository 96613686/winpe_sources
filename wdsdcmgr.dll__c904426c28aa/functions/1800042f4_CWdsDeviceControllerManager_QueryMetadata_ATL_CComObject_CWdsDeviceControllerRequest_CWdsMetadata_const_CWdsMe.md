# CWdsDeviceControllerManager::QueryMetadata(ATL::CComObject<CWdsDeviceControllerRequest> *,CWdsMetadata const *,CWdsMetadata *)

- ea: `0x1800042f4`
- end: `0x180004db6`
- name: `?QueryMetadata@CWdsDeviceControllerManager@@QEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@PEBVCWdsMetadata@@PEAV4@@Z`
- size: `2754`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int16 *, struct CWdsMetadata *, CWdsMetadata *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003398`

## callees

- `0x1800040ac`
- `0x1800042f4`
- `0x1800069dc`
- `0x180006ab0`
- `0x180006d90`
- `0x180006dfc`
- `0x1800070a4`
- `0x180007310`
- `0x180009838`
- `0x180009c30`
- `0x18000a5e8`
- `0x18000ad40`
- `0x18000adf4`
- `0x18000ae38`
- `0x18000b1a8`
- `0x18000b228`
- `0x18000b47c`
- `0x18000b834`
- `0x18000c2d0`
- `0x18000c8c4`
- `0x18000e194`
- `0x18000e504`
- `0x18000e65c`
- `0x180012f34`
- `0x1800134f4`
- `0x180014248`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x180015660`
- `0x180015c9d`
- `0x180015cc0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004492`
- `msvcrt!_wcsicmp` at `0x1800044ac`
- `msvcrt!_wcsicmp` at `0x180004492`
- `msvcrt!_wcsicmp` at `0x1800044ac`
- `KERNEL32!EnterCriticalSection` at `0x18000433c`
- `KERNEL32!EnterCriticalSection` at `0x18000433c`
- `KERNEL32!LeaveCriticalSection` at `0x180004408`
- `KERNEL32!LeaveCriticalSection` at `0x180004d6a`
- `KERNEL32!LeaveCriticalSection` at `0x180004408`
- `KERNEL32!LeaveCriticalSection` at `0x180004d6a`
- `WDSSRV!WdsPerfCounterAdd` at `0x180004c10`
- `WDSSRV!WdsPerfCounterAdd` at `0x180004c1b`
- `WDSSRV!WdsPerfCounterAdd` at `0x180004c10`
- `WDSSRV!WdsPerfCounterAdd` at `0x180004c1b`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::QueryMetadata(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int16 *a2,
        struct CWdsMetadata *a3,
        CWdsMetadata *a4)
{
  struct CWdsMetadata *v4; // r12
  int v5; // r14d
  LPCRITICAL_SECTION v6; // r15
  const char *v7; // rdx
  LONG LockCount; // esi
  int v9; // r13d
  wchar_t *v10; // rdi
  int appended; // ebx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  void *v16; // rsi
  unsigned int v17; // r15d
  const char *v18; // rdx
  void *v19; // rcx
  unsigned int v20; // r12d
  __int64 v21; // r14
  _QWORD *v22; // rdi
  unsigned __int16 *v23; // r15
  const char *v24; // rdx
  const char *v25; // rdx
  const char *v26; // rdx
  unsigned int DeviceIdDuidAlternateForm; // eax
  __int64 v28; // rdx
  int v29; // esi
  const char *v30; // rdx
  const char *v31; // rdx
  const char *v32; // rdx
  void *v33; // rcx
  void *v34; // rcx
  const char *v35; // rdx
  unsigned int v36; // r14d
  const char *v37; // rdx
  const char *v38; // rdx
  struct CWdsMetadata *v39; // rdi
  const char *v40; // rdx
  const char *v41; // rdx
  const char *v42; // rdx
  const char *v43; // rdx
  void *v44; // rsi
  const char *v45; // rdx
  const char *v46; // rdx
  int v47; // ecx
  unsigned int v48; // r15d
  __int64 v49; // r14
  __int64 v50; // rsi
  const unsigned __int16 *v51; // r12
  const char *v52; // rdx
  const char *v53; // rdx
  const char *v54; // rdx
  const char *v55; // rdx
  const char *v56; // rdx
  const char *v57; // rdx
  struct CWdsMetadata *v58; // rdi
  bool v59; // zf
  unsigned int v60; // eax
  const char *v61; // rdx
  unsigned int v62; // eax
  unsigned __int16 *v63; // rsi
  unsigned int v64; // eax
  const char *v65; // rdx
  int v66; // ecx
  __int64 *v67; // rdx
  int v68; // r9d
  int v69; // edi
  char v71; // [rsp+20h] [rbp-E0h]
  struct CWdsMetadata *v72; // [rsp+30h] [rbp-D0h] BYREF
  void *v73; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v74; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v75; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+58h] [rbp-A8h] BYREF
  int v77; // [rsp+5Ch] [rbp-A4h]
  CWdsComMetadataBuilder *v78; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  __int64 v80; // [rsp+70h] [rbp-90h]
  __int64 v81; // [rsp+78h] [rbp-88h]
  struct CWdsDeviceControllerManager::CQueryEntry *v82; // [rsp+80h] [rbp-80h] BYREF
  CWdsMetadata *v83; // [rsp+88h] [rbp-78h]
  int v84[2]; // [rsp+90h] [rbp-70h]
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+98h] [rbp-68h]
  CMRSWLock *v86; // [rsp+A0h] [rbp-60h] BYREF
  int v87; // [rsp+A8h] [rbp-58h]
  int v88; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *String1; // [rsp+B8h] [rbp-48h]
  __int64 v90; // [rsp+C0h] [rbp-40h]
  _QWORD v91[10]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v92[10]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v93[8]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v94; // [rsp+1F0h] [rbp+F0h]
  _OWORD v95[8]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v96; // [rsp+280h] [rbp+180h] BYREF

  v83 = a4;
  v4 = a3;
  v72 = a3;
  v5 = (int)a2;
  v75 = a2;
  v6 = lpCriticalSection;
  lpCriticalSectiona = lpCriticalSection;
  EnterCriticalSection(lpCriticalSection);
  LockCount = v6[8].LockCount;
  v86 = (CMRSWLock *)&v6[1];
  v77 = 1;
  v9 = 0;
  v87 = 0;
  v10 = 0;
  *(_QWORD *)v84 = 0;
  v78 = 0;
  v88 = 0;
  String1 = 0;
  v90 = 0;
  v91[0] = 0;
  v91[1] = 0;
  v91[3] = 0;
  v91[4] = 0;
  v91[6] = 0;
  v91[7] = 0;
  v92[0] = 0;
  v92[1] = 0;
  v92[3] = 0;
  v92[4] = 0;
  v92[6] = 0;
  v92[7] = 0;
  if ( !v6[5].LockCount )
  {
    appended = 5023;
    if ( ElValidateWin32(0x139Fu, v7, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x627u) )
      goto LABEL_101;
  }
  appended = CWdsMetadata::AppendAll((CWdsMetadata *)v92, (const struct CWdsMetadata *)&v6[6].LockCount);
  if ( ElValidateWin32(appended, v12, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x62Bu) )
    goto LABEL_101;
  v77 = 0;
  LeaveCriticalSection(v6);
  appended = CWdsMetadata::QueryRequired(v4, L"WDS.Request.Type", 1, &v88);
  if ( ElValidateWin32(appended, v13, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x636u) )
    goto LABEL_101;
  appended = 0;
  if ( v88 == 1 )
    v10 = String1;
  else
    appended = ElValidateWin32(0xDu, v14, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x60Fu);
  if ( ElValidateWin32(appended, v14, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x639u) )
    goto LABEL_101;
  if ( !_wcsicmp(v10, L"PXE") )
  {
LABEL_56:
    v39 = v83;
    appended = CWdsMetadata::Merge(v83, (const struct CWdsMetadata *)v92);
    if ( ElValidateWin32(appended, v40, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x6ABu) )
      goto LABEL_100;
    appended = CWdsComMetadata::CreateInstance(v4);
    if ( (int)ElValidateHr(
                appended,
                v41,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0x6B3u) < 0
      || (appended = CWdsComMetadataBuilder::CreateInstance(v39),
          (int)ElValidateHr(
                 appended,
                 v42,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x6B6u) < 0) )
    {
      if ( appended < 0 && (appended & 0x1FFF0000) == 0x70000 )
        appended = (unsigned __int16)appended;
      goto LABEL_100;
    }
    CAutoReaderLock::Lock((CAutoReaderLock *)&v86);
    if ( CWdsMetadata::CountInstancesOfTag(v4, L"WDS.DeviceController.Name") )
    {
      Block = 0;
      v80 = 0;
      v44 = 0;
      v73 = 0;
      v74 = 0;
      appended = CWdsMetadata::GetInstancesOfTag(v4, L"WDS.DeviceController.Name", &Block);
      if ( ElValidateWin32(
             appended,
             v45,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x6D6u) )
      {
        v34 = Block;
        if ( !Block )
          goto LABEL_100;
        goto LABEL_42;
      }
      v48 = HIDWORD(v80);
      v49 = 0;
      v22 = Block;
      if ( HIDWORD(v80) )
      {
        while ( 1 )
        {
          v50 = 0;
          v51 = 0;
          v82 = 0;
          appended = 0;
          if ( (unsigned int)v49 < v48 )
            v50 = v22[v49];
          else
            appended = 1413;
          if ( ElValidateWin32(
                 appended,
                 v46,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x6DFu) )
          {
            goto LABEL_38;
          }
          if ( *(_DWORD *)(v50 + 32) || *(_DWORD *)(v50 + 40) != 1 )
          {
            appended = 13;
            if ( ElValidateWin32(
                   0xDu,
                   v52,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                   0x6E4u) )
            {
              goto LABEL_38;
            }
          }
          appended = 0;
          if ( *(_DWORD *)(v50 + 40) == 1 )
            v51 = *(const unsigned __int16 **)(v50 + 48);
          else
            appended = ElValidateWin32(0xDu, v52, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x60Fu);
          if ( ElValidateWin32(
                 appended,
                 v52,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x6E8u) )
          {
            goto LABEL_38;
          }
          appended = CWdsDeviceControllerManager::GetQueryEntry(
                       (CWdsDeviceControllerManager *)lpCriticalSectiona,
                       v51,
                       &v82);
          if ( ElValidateWin32(
                 appended,
                 v53,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x6EFu) )
          {
            goto LABEL_38;
          }
          appended = CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone>::AddItem(&v73, v82);
          if ( ElValidateWin32(
                 appended,
                 v54,
                 "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                 0x6F2u) )
          {
            goto LABEL_38;
          }
          v49 = (unsigned int)(v49 + 1);
          if ( (unsigned int)v49 >= v48 )
          {
            v44 = v73;
            break;
          }
        }
      }
      appended = CWdsDeviceControllerManager::QueryMetadataWithSelectedControllers<CDeallocateNone>(
                   v47,
                   (_DWORD)v75,
                   (unsigned int)&v73,
                   v9,
                   *(__int64 *)v84,
                   (__int64)v78);
      if ( ElValidateWin32(
             appended,
             v55,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x6FAu) )
      {
        if ( !v44 )
          goto LABEL_40;
        v33 = v44;
        goto LABEL_39;
      }
      if ( v44 )
        operator delete(v44);
      if ( v22 )
        operator delete(v22);
      v39 = v83;
    }
    else
    {
      appended = CWdsDeviceControllerManager::QueryMetadataWithSelectedControllers<CDeallocateNone>(
                   0,
                   v5,
                   (int)v6 + 160,
                   v9,
                   *(__int64 *)v84,
                   (__int64)v78);
      if ( ElValidateWin32(
             appended,
             v43,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x6C9u) )
      {
        goto LABEL_100;
      }
    }
    if ( v87 )
    {
      if ( !--v87 )
        CMRSWLock::ReaderRelease(v86);
    }
    appended = CWdsMetadata::Clear(v39);
    if ( !ElValidateWin32(
            appended,
            v56,
            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
            0x700u) )
    {
      appended = CWdsComMetadataBuilder::GetMetadata(v78, v39);
      if ( !ElValidateWin32(
              appended,
              v57,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x703u) )
      {
        WdsPerfCounterAdd(48);
        WdsPerfCounterAdd(50);
      }
    }
    goto LABEL_100;
  }
  if ( _wcsicmp(v10, L"Deployment") )
  {
    appended = 13;
    if ( ElValidateWin32(0xDu, v15, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x6A0u) )
      goto LABEL_101;
    goto LABEL_56;
  }
  v9 = 1;
  if ( !LockCount )
    goto LABEL_56;
  Block = 0;
  v80 = 0;
  v73 = 0;
  v16 = 0;
  v74 = 0;
  v17 = 0;
  appended = CWdsMetadata::GetInstancesOfTag(v4, L"WDS.Device.ID", &Block);
  if ( ElValidateWin32(appended, v18, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x651u) )
  {
    v19 = Block;
    if ( !Block )
      goto LABEL_101;
    goto LABEL_14;
  }
  v20 = HIDWORD(v80);
  v21 = 0;
  v22 = Block;
  if ( HIDWORD(v80) )
  {
    v23 = v75;
    while ( 1 )
    {
      memset_0(v95, 0, 0x88u);
      memset_0(v93, 0, 0x88u);
      LODWORD(v82) = 0;
      appended = 0;
      v76 = 0;
      if ( (unsigned int)v21 < v20 )
        v23 = (unsigned __int16 *)v22[v21];
      else
        appended = 1413;
      if ( ElValidateWin32(
             appended,
             v24,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x662u) )
      {
        break;
      }
      if ( *((_DWORD *)v23 + 8) )
      {
        appended = 13;
        if ( ElValidateWin32(0xDu, v25, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x667u) )
          break;
      }
      appended = CWdsMetadataValue::GetBinaryValue((CWdsMetadataValue *)(v23 + 20), (unsigned __int8 *)v95, 0x80u, &v96);
      if ( ElValidateWin32(
             appended,
             v26,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x66Eu) )
      {
        break;
      }
      Block = 0;
      v80 = 0;
      v81 = 0;
      if ( v96 == 16 )
      {
        v28 = 128;
        v29 = 0;
        v93[0] = v95[0];
        v93[1] = v95[1];
        v93[2] = v95[2];
        v93[3] = v95[3];
        v93[4] = v95[4];
        v93[5] = v95[5];
        v93[6] = v95[6];
        v93[7] = v95[7];
        v94 = 16;
        appended = 0;
      }
      else
      {
        DeviceIdDuidAlternateForm = GetDeviceIdDuidAlternateForm(
                                      (const struct _WDS_DEVICE_ID *)v95,
                                      (int *)&v82,
                                      &v76,
                                      (struct _WDS_DEVICE_ID *)v93);
        v29 = v76;
        appended = DeviceIdDuidAlternateForm;
      }
      if ( ElValidateWin32(
             appended,
             (const char *)v28,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x674u) )
      {
        break;
      }
      appended = AddDeviceIdIfNotPresent(&v73, v95);
      if ( ElValidateWin32(
             appended,
             v30,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0x677u) )
      {
        break;
      }
      if ( v29 )
      {
        appended = AddDeviceIdIfNotPresent(&v73, v93);
        if ( ElValidateWin32(
               appended,
               v31,
               "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
               0x67Eu) )
        {
          break;
        }
      }
      v21 = (unsigned int)(v21 + 1);
      if ( (unsigned int)v21 >= v20 )
      {
        v17 = HIDWORD(v74);
        v16 = v73;
        goto LABEL_33;
      }
    }
LABEL_38:
    v33 = v73;
    if ( !v73 )
    {
LABEL_40:
      if ( !v22 )
      {
LABEL_100:
        v4 = v72;
        goto LABEL_101;
      }
      v34 = v22;
LABEL_42:
      operator delete(v34);
      goto LABEL_100;
    }
LABEL_39:
    operator delete(v33);
    goto LABEL_40;
  }
LABEL_33:
  v4 = v72;
  appended = CWdsMetadata::AppendAll((CWdsMetadata *)v91, v72);
  if ( ElValidateWin32(appended, v32, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x687u) )
    goto LABEL_34;
  appended = CWdsMetadata::RemoveInstancesOfTag((CWdsMetadata *)v91, L"WDS.Device.ID");
  if ( ElValidateWin32(appended, v35, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x68Au) )
    goto LABEL_34;
  v36 = 0;
  if ( !v17 )
  {
LABEL_51:
    v4 = (struct CWdsMetadata *)v91;
    v72 = (struct CWdsMetadata *)v91;
    if ( v16 )
      operator delete(v16);
    if ( v22 )
      operator delete(v22);
    LODWORD(v6) = (_DWORD)lpCriticalSectiona;
    v5 = (int)v75;
    goto LABEL_56;
  }
  while ( 1 )
  {
    memset_0(v93, 0, 0x88u);
    appended = v36 < v17 ? CDynArray<_WDS_DEVICE_ID,CDeallocateNone>::GetItem(&v73, v36, v93) : 1413;
    if ( ElValidateWin32(appended, v37, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x691u) )
      break;
    appended = CWdsMetadata::AppendBinaryEntry((CWdsMetadata *)v91, L"WDS.Device.ID", (unsigned __int8 *)v93, v94);
    if ( ElValidateWin32(appended, v38, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x697u) )
      break;
    if ( ++v36 >= v17 )
      goto LABEL_51;
  }
LABEL_34:
  if ( v16 )
    operator delete(v16);
  if ( v22 )
  {
    v19 = v22;
LABEL_14:
    operator delete(v19);
  }
LABEL_101:
  v75 = 0;
  v58 = 0;
  v72 = 0;
  if ( appended )
    v59 = (byte_18001DD41 & 0x10) == 0;
  else
    v59 = (byte_18001DD41 & 8) == 0;
  if ( v59 )
    goto LABEL_118;
  v60 = CWdsMetadata::ToLines(v4, &v75);
  v62 = ElValidateWin32(v60, v61, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x78Cu);
  v63 = v75;
  if ( !v62 )
  {
    v64 = CWdsMetadata::ToLines(v83, (unsigned __int16 **)&v72);
    if ( !ElValidateWin32(v64, v65, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x78Fu) )
    {
      if ( appended )
      {
        if ( (byte_18001DD41 & 0x10) != 0 )
        {
          v71 = appended;
          v67 = MetadataQueryFailed;
          goto LABEL_110;
        }
      }
      else if ( (byte_18001DD41 & 8) != 0 )
      {
        v71 = 0;
        v67 = MetadataQuery;
LABEL_110:
        v58 = v72;
        McTemplateU0zzd(v66, (_DWORD)v67, (_DWORD)v63, (_DWORD)v72, v71);
        goto LABEL_114;
      }
    }
    v58 = v72;
  }
LABEL_114:
  if ( v63 )
    operator delete(v63);
  if ( v58 )
    operator delete(v58);
LABEL_118:
  if ( *(_QWORD *)v84 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v84 + 16LL))(*(_QWORD *)v84);
  if ( v78 )
    (*(void (__fastcall **)(CWdsComMetadataBuilder *))(*(_QWORD *)v78 + 16LL))(v78);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v92);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v91);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v88);
  if ( v87 == 1 )
    CMRSWLock::ReaderRelease(v86);
  if ( v77 )
  {
    v69 = v77 - 1;
    if ( v77 == 1 )
      LeaveCriticalSection(lpCriticalSectiona);
    if ( v69 )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", v68, 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800042f4  push    rbp
0x1800042f6  push    rbx
0x1800042f7  push    rsi
0x1800042f8  push    rdi
0x1800042f9  push    r12
0x1800042fb  push    r13
0x1800042fd  push    r14
0x1800042ff  push    r15
0x180004301  lea     rbp, [rsp-1A8h]
0x180004309  sub     rsp, 2A8h
0x180004310  mov     rax, cs:__security_cookie
0x180004317  xor     rax, rsp
0x18000431a  mov     [rbp+1E0h+var_50], rax
0x180004321  mov     [rbp+1E0h+var_258], r9
0x180004325  mov     r12, r8
0x180004328  mov     [rsp+2E0h+var_2B0], r8
0x18000432d  mov     r14, rdx
0x180004330  mov     [rsp+2E0h+var_290], rdx
0x180004335  mov     r15, rcx
0x180004338  mov     [rbp+1E0h+lpCriticalSection], rcx
0x18000433c  call    cs:__imp_EnterCriticalSection
0x180004342  mov     esi, [r15+148h]
0x180004349  lea     rax, [r15+28h]
0x18000434d  xor     ecx, ecx
0x18000434f  mov     [rbp+1E0h+var_240], rax
0x180004353  xor     eax, eax
0x180004355  mov     [rsp+2E0h+var_284], 1
0x18000435d  mov     r13d, ecx
0x180004360  mov     [rbp+1E0h+var_238], ecx
0x180004363  mov     edi, ecx
0x180004365  mov     qword ptr [rbp+1E0h+var_250], rcx
0x180004369  mov     [rsp+2E0h+var_280], rcx
0x18000436e  mov     [rbp+1E0h+var_230], ecx
0x180004371  mov     [rbp+1E0h+String1], rax
0x180004375  mov     [rbp+1E0h+var_220], rax
0x180004379  mov     [rbp+1E0h+var_210], rcx
0x18000437d  mov     [rbp+1E0h+var_208], rcx
0x180004381  mov     [rbp+1E0h+var_1F8], rcx
0x180004385  mov     [rbp+1E0h+var_1F0], rcx
0x180004389  mov     [rbp+1E0h+var_1E0], rcx
0x18000438d  mov     [rbp+1E0h+var_1D8], rcx
0x180004391  mov     [rbp+1E0h+var_1C0], rcx
0x180004395  mov     [rbp+1E0h+var_1B8], rcx
0x180004399  mov     [rbp+1E0h+var_1A8], rcx
0x18000439d  mov     [rbp+1E0h+var_1A0], rcx
0x1800043a1  mov     [rbp+1E0h+var_190], rcx
0x1800043a5  mov     [rbp+1E0h+var_188], rcx
0x1800043a9  cmp     [r15+0D0h], ecx
0x1800043b0  jnz     short loc_1800043D3
0x1800043b2  mov     ebx, 139Fh
0x1800043b7  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800043be  mov     ecx, ebx; unsigned int
0x1800043c0  mov     r9d, 627h; unsigned int
0x1800043c6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800043cb  test    eax, eax
0x1800043cd  jnz     loc_180004C26
0x1800043d3  lea     rdx, [r15+0F8h]; struct CWdsMetadata *
0x1800043da  lea     rcx, [rbp+1E0h+var_1C0]; this
0x1800043de  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x1800043e3  mov     r9d, 62Bh; unsigned int
0x1800043e9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800043f0  mov     ecx, eax; unsigned int
0x1800043f2  mov     ebx, eax
0x1800043f4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800043f9  test    eax, eax
0x1800043fb  jnz     loc_180004C26
0x180004401  mov     rcx, r15; lpCriticalSection
0x180004404  mov     [rsp+2E0h+var_284], eax
0x180004408  call    cs:__imp_LeaveCriticalSection
0x18000440e  lea     r9, [rbp+1E0h+var_230]
0x180004412  mov     r8d, 1
0x180004418  lea     rdx, aWdsRequestType; "WDS.Request.Type"
0x18000441f  mov     rcx, r12
0x180004422  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180004427  mov     r9d, 636h; unsigned int
0x18000442d  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004434  mov     ecx, eax; unsigned int
0x180004436  mov     ebx, eax
0x180004438  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000443d  test    eax, eax
0x18000443f  jnz     loc_180004C26
0x180004445  xor     ebx, ebx
0x180004447  cmp     [rbp+1E0h+var_230], 1
0x18000444b  jnz     short loc_180004453
0x18000444d  mov     rdi, [rbp+1E0h+String1]
0x180004451  jmp     short loc_18000446C
0x180004453  mov     r9d, 60Fh; unsigned int
0x180004459  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180004460  mov     ecx, 0Dh; unsigned int
0x180004465  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000446a  mov     ebx, eax
0x18000446c  mov     r9d, 639h; unsigned int
0x180004472  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004479  mov     ecx, ebx; unsigned int
0x18000447b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004480  test    eax, eax
0x180004482  jnz     loc_180004C26
0x180004488  lea     rdx, aPxe; "PXE"
0x18000448f  mov     rcx, rdi; String1
0x180004492  call    cs:__imp__wcsicmp
0x180004498  xor     ebx, ebx
0x18000449a  test    eax, eax
0x18000449c  jz      loc_18000488F
0x1800044a2  lea     rdx, aDeployment; "Deployment"
0x1800044a9  mov     rcx, rdi; String1
0x1800044ac  call    cs:__imp__wcsicmp
0x1800044b2  test    eax, eax
0x1800044b4  jnz     loc_180004905
0x1800044ba  lea     r13d, [rbx+1]
0x1800044be  test    esi, esi
0x1800044c0  jz      loc_18000488F
0x1800044c6  lea     r8, [rsp+2E0h+Block]
0x1800044cb  mov     [rsp+2E0h+Block], rbx
0x1800044d0  lea     rdx, aWdsDeviceId; "WDS.Device.ID"
0x1800044d7  mov     [rsp+2E0h+var_270], rbx
0x1800044dc  mov     rcx, r12
0x1800044df  mov     [rsp+2E0h+var_2A8], rbx
0x1800044e4  mov     esi, ebx
0x1800044e6  mov     [rsp+2E0h+var_2A0], rbx
0x1800044eb  mov     r15d, ebx
0x1800044ee  call    ?GetInstancesOfTag@CWdsMetadata@@QEBAKPEBGPEAV?$CDynArray@PEBVCWdsMetadataEntry@@VCDeallocateNone@@@@@Z; CWdsMetadata::GetInstancesOfTag(ushort const *,CDynArray<CWdsMetadataEntry const *,CDeallocateNone> *)
0x1800044f3  mov     r9d, 651h; unsigned int
0x1800044f9  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180004500  mov     ecx, eax; unsigned int
0x180004502  mov     ebx, eax
0x180004504  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004509  test    eax, eax
0x18000450b  jz      short loc_180004525
0x18000450d  mov     rcx, [rsp+2E0h+Block]; Block
0x180004512  test    rcx, rcx
0x180004515  jz      loc_180004C26
0x18000451b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004520  jmp     loc_180004C26
0x180004525  mov     r12d, dword ptr [rsp+2E0h+var_270+4]
0x18000452a  xor     r14d, r14d
0x18000452d  mov     rdi, [rsp+2E0h+Block]
0x180004532  test    r12d, r12d
0x180004535  jz      loc_18000472E
0x18000453b  mov     r15, [rsp+2E0h+var_290]
0x180004540  xor     edx, edx; Val
0x180004542  lea     rcx, [rbp+1E0h+var_E0]; void *
0x180004549  mov     r8d, 88h; Size
0x18000454f  call    memset_0
0x180004554  xor     edx, edx; Val
0x180004556  lea     rcx, [rbp+1E0h+var_170]; void *
0x18000455a  mov     r8d, 88h; Size
0x180004560  call    memset_0
0x180004565  and     dword ptr [rbp+1E0h+var_260], 0
0x180004569  xor     ebx, ebx
0x18000456b  and     [rsp+2E0h+var_288], 0
0x180004570  cmp     r14d, r12d
0x180004573  jb      short loc_18000457C
0x180004575  mov     ebx, 585h
0x18000457a  jmp     short loc_180004580
0x18000457c  mov     r15, [rdi+r14*8]
0x180004580  mov     r9d, 662h; unsigned int
0x180004586  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000458d  mov     ecx, ebx; unsigned int
0x18000458f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004594  test    eax, eax
0x180004596  jnz     loc_180004777
0x18000459c  cmp     [r15+20h], eax
0x1800045a0  jz      short loc_1800045C5
0x1800045a2  mov     eax, 0Dh
0x1800045a7  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800045ae  mov     ecx, eax; unsigned int
0x1800045b0  mov     r9d, 667h; unsigned int
0x1800045b6  mov     ebx, eax
0x1800045b8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800045bd  test    eax, eax
0x1800045bf  jnz     loc_180004777
0x1800045c5  lea     rcx, [r15+28h]; this
0x1800045c9  mov     r8d, 80h; unsigned __int64
0x1800045cf  lea     r9, [rbp+1E0h+var_60]; unsigned __int64 *
0x1800045d6  lea     rdx, [rbp+1E0h+var_E0]; unsigned __int8 *
0x1800045dd  call    ?GetBinaryValue@CWdsMetadataValue@@QEBAKPEAE_KPEA_K@Z; CWdsMetadataValue::GetBinaryValue(uchar *,unsigned __int64,unsigned __int64 *)
0x1800045e2  mov     r9d, 66Eh; unsigned int
0x1800045e8  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800045ef  mov     ecx, eax; unsigned int
0x1800045f1  mov     ebx, eax
0x1800045f3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800045f8  test    eax, eax
0x1800045fa  jnz     loc_180004777
0x180004600  xor     eax, eax
0x180004602  cmp     [rbp+1E0h+var_60], 10h
0x18000460a  mov     [rsp+2E0h+Block], rax
0x18000460f  mov     [rsp+2E0h+var_270], rax
0x180004614  mov     [rsp+2E0h+var_268], rax
0x180004619  jz      short loc_180004646
0x18000461b  lea     rax, [rsp+2E0h+Block]
0x180004620  lea     r9, [rbp+1E0h+var_170]; struct _WDS_DEVICE_ID *
0x180004624  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180004629  lea     r8, [rsp+2E0h+var_288]; int *
0x18000462e  lea     rdx, [rbp+1E0h+var_260]; int *
0x180004632  lea     rcx, [rbp+1E0h+var_E0]; struct _WDS_DEVICE_ID *
0x180004639  call    ?GetDeviceIdDuidAlternateForm@@YAKPEBU_WDS_DEVICE_ID@@PEAH1PEAU1@@Z; GetDeviceIdDuidAlternateForm(_WDS_DEVICE_ID const *,int *,int *,_WDS_DEVICE_ID *)
0x18000463e  mov     esi, [rsp+2E0h+var_288]
0x180004642  mov     ebx, eax
0x180004644  jmp     short loc_1800046A1
0x180004646  lea     rax, [rbp+1E0h+var_E0]
0x18000464d  mov     edx, 80h; char *
0x180004652  movups  xmm0, xmmword ptr [rax]
0x180004655  lea     rcx, [rbp+1E0h+var_170]
0x180004659  xor     esi, esi
0x18000465b  movups  xmm1, xmmword ptr [rax+10h]
0x18000465f  movups  xmmword ptr [rcx], xmm0
0x180004662  movups  xmm0, xmmword ptr [rax+20h]
0x180004666  movups  xmmword ptr [rcx+10h], xmm1
0x18000466a  movups  xmm1, xmmword ptr [rax+30h]
0x18000466e  movups  xmmword ptr [rcx+20h], xmm0
0x180004672  movups  xmm0, xmmword ptr [rax+40h]
0x180004676  movups  xmmword ptr [rcx+30h], xmm1
0x18000467a  movups  xmm1, xmmword ptr [rax+50h]
0x18000467e  movups  xmmword ptr [rcx+40h], xmm0
0x180004682  movups  xmm0, xmmword ptr [rax+60h]
0x180004686  movups  xmmword ptr [rcx+50h], xmm1
0x18000468a  movups  xmm1, xmmword ptr [rax+70h]
0x18000468e  mov     rax, [rax+rdx]
0x180004692  movups  xmmword ptr [rcx+60h], xmm0
0x180004696  movups  xmmword ptr [rcx+rdx-10h], xmm1
0x18000469b  mov     [rcx+rdx], rax
0x18000469f  xor     ebx, ebx
0x1800046a1  mov     r9d, 674h; unsigned int
0x1800046a7  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800046ae  mov     ecx, ebx; unsigned int
0x1800046b0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800046b5  test    eax, eax
0x1800046b7  jnz     loc_180004777
0x1800046bd  lea     rdx, [rbp+1E0h+var_E0]
0x1800046c4  lea     rcx, [rsp+2E0h+var_2A8]
0x1800046c9  call    AddDeviceIdIfNotPresent
0x1800046ce  mov     r9d, 677h; unsigned int
0x1800046d4  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800046db  mov     ecx, eax; unsigned int
0x1800046dd  mov     ebx, eax
0x1800046df  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800046e4  test    eax, eax
0x1800046e6  jnz     loc_180004777
0x1800046ec  test    esi, esi
0x1800046ee  jz      short loc_180004718
0x1800046f0  lea     rdx, [rbp+1E0h+var_170]
0x1800046f4  lea     rcx, [rsp+2E0h+var_2A8]
0x1800046f9  call    AddDeviceIdIfNotPresent
0x1800046fe  mov     r9d, 67Eh; unsigned int
0x180004704  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000470b  mov     ecx, eax; unsigned int
0x18000470d  mov     ebx, eax
0x18000470f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004714  test    eax, eax
0x180004716  jnz     short loc_180004777
0x180004718  inc     r14d
0x18000471b  cmp     r14d, r12d
0x18000471e  jb      loc_180004540
0x180004724  mov     r15d, dword ptr [rsp+2E0h+var_2A0+4]
0x180004729  mov     rsi, [rsp+2E0h+var_2A8]
0x18000472e  mov     r12, [rsp+2E0h+var_2B0]
0x180004733  lea     rcx, [rbp+1E0h+var_210]; this
0x180004737  mov     rdx, r12; struct CWdsMetadata *
0x18000473a  call    ?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z; CWdsMetadata::AppendAll(CWdsMetadata const *)
0x18000473f  mov     r9d, 687h; unsigned int
0x180004745  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000474c  mov     ecx, eax; unsigned int
0x18000474e  mov     ebx, eax
0x180004750  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004755  test    eax, eax
0x180004757  jz      short loc_18000479C
0x180004759  test    rsi, rsi
0x18000475c  jz      short loc_180004766
0x18000475e  mov     rcx, rsi; Block
0x180004761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004766  test    rdi, rdi
0x180004769  jz      loc_180004C26
0x18000476f  mov     rcx, rdi
0x180004772  jmp     loc_18000451B
0x180004777  mov     rcx, [rsp+2E0h+var_2A8]; Block
0x18000477c  test    rcx, rcx
0x18000477f  jz      short loc_180004786
0x180004781  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004786  test    rdi, rdi
0x180004789  jz      loc_180004C21
0x18000478f  mov     rcx, rdi; Block
0x180004792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004797  jmp     loc_180004C21
0x18000479c  lea     rdx, aWdsDeviceId; "WDS.Device.ID"
0x1800047a3  lea     rcx, [rbp+1E0h+var_210]; this
0x1800047a7  call    ?RemoveInstancesOfTag@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::RemoveInstancesOfTag(ushort const *)
0x1800047ac  mov     r9d, 68Ah; unsigned int
0x1800047b2  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800047b9  mov     ecx, eax; unsigned int
0x1800047bb  mov     ebx, eax
0x1800047bd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800047c2  test    eax, eax
0x1800047c4  jnz     short loc_180004759
0x1800047c6  xor     r14d, r14d
0x1800047c9  test    r15d, r15d
0x1800047cc  jz      loc_180004863
0x1800047d2  xor     edx, edx; Val
0x1800047d4  lea     rcx, [rbp+1E0h+var_170]; void *
0x1800047d8  mov     r8d, 88h; Size
0x1800047de  call    memset_0
  ... truncated ...
```
