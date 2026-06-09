# ConfigMgr::SetIdentificationObject(IWmiDbHandle *,IWmiDbSession *)

- ea: `0x180074908`
- end: `0x180075323`
- name: `?SetIdentificationObject@ConfigMgr@@SAJPEAUIWmiDbHandle@@PEAUIWmiDbSession@@@Z`
- size: `2587`
- prototype: `__int64 __fastcall(struct IWmiDbHandle *, struct IWmiDbSession *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a7250`

## callees

- `0x18000b140`
- `0x180011700`
- `0x18003cfe0`
- `0x18004b934`
- `0x180074908`
- `0x18007532c`
- `0x18007549c`
- `0x18007f7cc`
- `0x180085c70`
- `0x180086c50`
- `0x180088238`
- `0x180093be8`
- `0x1800b6f68`
- `0x1800ce4d2`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180074e8e`
- `msvcrt!swprintf_s` at `0x180074e8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074fef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075140`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074fef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075140`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074d0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074da0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074d0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074da0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800749b2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800749b2`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x180074cd9`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x180074fb6`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x180074cd9`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x180074fb6`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x180074ce7`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x180074ce7`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x180074cf0`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x180074cf0`
- `wbemcomn!GetMemLogObject` at `0x1800749da`
- `wbemcomn!GetMemLogObject` at `0x180074a6b`
- `wbemcomn!GetMemLogObject` at `0x180074afd`
- `wbemcomn!GetMemLogObject` at `0x180074b91`
- `wbemcomn!GetMemLogObject` at `0x180074c46`
- `wbemcomn!GetMemLogObject` at `0x180074d1d`
- `wbemcomn!GetMemLogObject` at `0x180074daa`
- `wbemcomn!GetMemLogObject` at `0x180074eba`
- `wbemcomn!GetMemLogObject` at `0x180074f45`
- `wbemcomn!GetMemLogObject` at `0x180074ff9`
- `wbemcomn!GetMemLogObject` at `0x1800750a8`
- `wbemcomn!GetMemLogObject` at `0x18007514a`
- `wbemcomn!GetMemLogObject` at `0x1800751dd`
- `wbemcomn!GetMemLogObject` at `0x1800752a8`
- `wbemcomn!GetMemLogObject` at `0x1800749da`
- `wbemcomn!GetMemLogObject` at `0x180074a6b`
- `wbemcomn!GetMemLogObject` at `0x180074afd`
- `wbemcomn!GetMemLogObject` at `0x180074b91`
- `wbemcomn!GetMemLogObject` at `0x180074c46`
- `wbemcomn!GetMemLogObject` at `0x180074d1d`
- `wbemcomn!GetMemLogObject` at `0x180074daa`
- `wbemcomn!GetMemLogObject` at `0x180074eba`
- `wbemcomn!GetMemLogObject` at `0x180074f45`
- `wbemcomn!GetMemLogObject` at `0x180074ff9`
- `wbemcomn!GetMemLogObject` at `0x1800750a8`
- `wbemcomn!GetMemLogObject` at `0x18007514a`
- `wbemcomn!GetMemLogObject` at `0x1800751dd`
- `wbemcomn!GetMemLogObject` at `0x1800752a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800749ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074a76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074b08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074b9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074c51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074d2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074dba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074ec5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074f50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180075009`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800750b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007515a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800751e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800752b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800749ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074a76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074b08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074b9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074c51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074d2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074dba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074ec5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180074f50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180075009`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800750b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007515a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800751e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800752b3`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x180074a5b`
- `FastProx!?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z` at `0x180074a5b`

## string_xrefs

- `0x180074ea1`: `VersionUsedToCreateDB`
- `0x180075134`: `Working Directory`
- `0x180074fe3`: `SetupDate`
- `0x18007508f`: `SetupDateTime`
- `0x1800751c4`: `WorkingDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ConfigMgr::SetIdentificationObject(struct IWmiDbHandle *a1, struct IWmiDbSession *a2)
{
  struct IWbemClassObject *v4; // r14
  struct IWbemClassObject *v5; // rax
  CTimerNextFiringClass *v6; // rax
  CProviderClass *FiringClass; // rbx
  CMemoryLog *MemLogObject; // rax
  int v10; // ebx
  const struct _GUID *v11; // r8
  CMemoryLog *v12; // rax
  int v13; // ebx
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  int v16; // ebx
  CMemoryLog *v17; // rax
  struct CWbemObject *v18; // r13
  const WCHAR *RegistryPathCIMOM; // rbx
  HKEY RegistryPathRoot; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  int v23; // ebx
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  const struct _GUID *v26; // r8
  CMemoryLog *v27; // rax
  unsigned __int64 v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  int v32; // ebx
  CMemoryLog *v33; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-3E8h]
  bool v35[4]; // [rsp+40h] [rbp-3C8h] BYREF
  int ObjectW; // [rsp+44h] [rbp-3C4h]
  DWORD cbData; // [rsp+48h] [rbp-3C0h] BYREF
  struct IWbemClassObject *v38; // [rsp+50h] [rbp-3B8h] BYREF
  HKEY v39; // [rsp+58h] [rbp-3B0h] BYREF
  DWORD Type; // [rsp+60h] [rbp-3A8h] BYREF
  struct IWbemClassObject *v41; // [rsp+68h] [rbp-3A0h] BYREF
  struct IWbemClassObject *v42; // [rsp+70h] [rbp-398h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-390h] BYREF
  HKEY v44; // [rsp+80h] [rbp-388h] BYREF
  CProviderClass *v45; // [rsp+88h] [rbp-380h] BYREF
  void *v46; // [rsp+90h] [rbp-378h] BYREF
  void *v47; // [rsp+98h] [rbp-370h] BYREF
  _WORD v48[120]; // [rsp+A0h] [rbp-368h] BYREF
  wchar_t Buffer[24]; // [rsp+190h] [rbp-278h] BYREF
  BYTE Data[2]; // [rsp+1C0h] [rbp-248h] BYREF

  v35[0] = 0;
  v42 = 0;
  ObjectW = CRepository::GetObjectW(a2, a1, L"__CIMOMIdentification=@", 0, &v42);
  v4 = v42;
  if ( !v42 )
  {
    v35[0] = 1;
    v41 = 0;
    ObjectW = CRepository::GetObjectW(a2, a1, L"__CIMOMIdentification", 0, &v41);
    v5 = v41;
    if ( !v41 )
    {
      v6 = (CTimerNextFiringClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
      v44 = (HKEY)v6;
      if ( v6 )
        FiringClass = CTimerNextFiringClass::CTimerNextFiringClass(v6);
      else
        FiringClass = 0;
      if ( !FiringClass )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            2147749894LL);
        }
        return 2147749894LL;
      }
      v45 = FiringClass;
      CIdentificationClass::Init(FiringClass);
      v46 = 0;
      v10 = CWbemObject::QueryInterface(FiringClass, &IID_IWbemClassObject, &v46);
      ObjectW = v10;
      if ( v10 < 0 )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v10);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)v10);
        }
        CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v45);
        return (unsigned int)v10;
      }
      v47 = v46;
      v13 = CRepository::PutObject(a2, a1, v11, v46, 0x1000u);
      ObjectW = v13;
      if ( v13 < 0 )
      {
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, v13);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)v13);
        }
LABEL_23:
        CReleaseMe::release((CReleaseMe *)&v47);
        CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v45);
        return (unsigned int)v13;
      }
      v13 = CRepository::GetObjectW(a2, a1, L"__CIMOMIdentification", 0, &v41);
      ObjectW = v13;
      if ( v13 < 0 )
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, v13);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
            (unsigned int)v13);
        }
        goto LABEL_23;
      }
      CReleaseMe::release((CReleaseMe *)&v47);
      CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(&v45);
      v5 = v41;
    }
    v44 = (HKEY)v5;
    v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v41->lpVtbl->SpawnInstance)(
            v41,
            0,
            &v42);
    ObjectW = v16;
    if ( v16 < 0 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, v16);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v16);
      }
      CReleaseMe::release((CReleaseMe *)&v44);
      return (unsigned int)v16;
    }
    CReleaseMe::release((CReleaseMe *)&v44);
    v4 = v42;
  }
  v38 = v4;
  v18 = (struct CWbemObject *)v42;
  memset_0(Data, 0, 0x20Au);
  hKey = 0;
  if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    RegistryPathCIMOM = (const WCHAR *)CWbemInstallObject::GetRegistryPathCIMOM();
    RegistryPathRoot = (HKEY)CWbemInstallObject::GetRegistryPathRoot();
    if ( RegOpenKeyExW(RegistryPathRoot, RegistryPathCIMOM, 0, 0x2000000u, &hKey) )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, -2147217407);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749889LL);
      }
LABEL_44:
      CReleaseMe::release((CReleaseMe *)&v38);
      return 2147749889LL;
    }
  }
  else if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"software\\microsoft\\wbem\\cimom", 0, 0x2000000u, &hKey) )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749889LL);
    }
    goto LABEL_44;
  }
  v44 = hKey;
  v39 = hKey;
  memset_0(v48, 0, 0xE8u);
  RtlGetVersionResource(&_ImageBase, 0, 2u, (struct _RTL_VERSION_RESOURCE *)v48);
  LODWORD(phkResult) = v48[1];
  swprintf_s(Buffer, 0x18u, L"%u.%u.%u.%u", v48[0], phkResult, v48[2], v48[3]);
  v23 = PutValueIfDiff(v18, L"VersionUsedToCreateDB", Buffer, v35);
  ObjectW = v23;
  if ( v23 < 0 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, v23);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v23);
    }
LABEL_88:
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v39);
    CReleaseMe::release((CReleaseMe *)&v38);
    return (unsigned int)v23;
  }
  v23 = PutValueIfDiff(v18, L"VersionCurrentlyRunning", Buffer, v35);
  ObjectW = v23;
  if ( v23 < 0 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, v23);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
        (unsigned int)v23);
    }
    goto LABEL_88;
  }
  cbData = 520;
  Type = 0;
  if ( !(unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    if ( RegQueryValueExW(hKey, L"SetupDate", 0, &Type, Data, &cbData) )
    {
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, -2147217407);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749889LL);
      }
LABEL_69:
      CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v39);
      CReleaseMe::release((CReleaseMe *)&v38);
      return 2147749889LL;
    }
    v28 = cbData & 0xFFFFFFFE;
    if ( v28 >= 0x20A )
      _report_rangecheckfailure();
    *(_WORD *)&Data[v28] = 0;
    v23 = PutValueIfDiff(v18, L"SetupDateTime", (unsigned __int16 *)Data, v35);
    ObjectW = v23;
    if ( v23 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v23);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v23);
      }
      goto LABEL_88;
    }
    cbData = 522;
    if ( RegQueryValueExW(hKey, L"Working Directory", 0, &Type, Data, &cbData) )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, -2147217407);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749889LL);
      }
      goto LABEL_69;
    }
    v23 = PutValueIfDiff(v18, L"WorkingDirectory", (unsigned __int16 *)Data, v35);
    ObjectW = v23;
    if ( v23 < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v23);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
          (unsigned int)v23);
      }
      goto LABEL_88;
    }
  }
  if ( v35[0] )
  {
    v32 = CRepository::PutObject(a2, a1, v26, v18, 0x1000u);
    ObjectW = v32;
  }
  else
  {
    v32 = 0;
    ObjectW = 0;
  }
  if ( v44 )
    DLRegCloseKey();
  if ( v4 )
    ((void (__fastcall *)(struct IWbemClassObject *))v4->lpVtbl->Release)(v4);
  v38 = 0;
  if ( v32 < 0 )
  {
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, v32);
  }
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids,
      (unsigned int)v32);
  }
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x180074908  mov     [rsp+arg_10], rbx
0x18007490d  push    rdi
0x18007490e  push    r12
0x180074910  push    r13
0x180074912  push    r14
0x180074914  push    r15
0x180074916  sub     rsp, 3E0h
0x18007491d  mov     rax, cs:__security_cookie
0x180074924  xor     rax, rsp
0x180074927  mov     [rsp+408h+var_38], rax
0x18007492f  mov     r12, rdx
0x180074932  mov     r15, rcx
0x180074935  xor     edi, edi
0x180074937  mov     [rsp+408h+var_3C8], dil
0x18007493c  mov     [rsp+408h+var_398], rdi
0x180074941  lea     rax, [rsp+408h+var_398]
0x180074946  mov     [rsp+408h+phkResult], rax; struct IWbemClassObject **
0x18007494b  xor     r9d, r9d; unsigned int
0x18007494e  lea     r8, aCimomidentific; "__CIMOMIdentification=@"
0x180074955  mov     rdx, rcx; struct IWmiDbHandle *
0x180074958  mov     rcx, r12; struct IWmiDbSession *
0x18007495b  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x180074960  mov     [rsp+408h+var_3C4], eax
0x180074964  mov     r14, [rsp+408h+var_398]
0x180074969  test    r14, r14
0x18007496c  jnz     loc_180074CB5
0x180074972  mov     [rsp+408h+var_3C8], 1
0x180074977  mov     [rsp+408h+var_3A0], rdi
0x18007497c  lea     rax, [rsp+408h+var_3A0]
0x180074981  mov     [rsp+408h+phkResult], rax; struct IWbemClassObject **
0x180074986  xor     r9d, r9d; unsigned int
0x180074989  lea     r8, aCimomidentific_0; "__CIMOMIdentification"
0x180074990  mov     rdx, r15; struct IWmiDbHandle *
0x180074993  mov     rcx, r12; struct IWmiDbSession *
0x180074996  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x18007499b  mov     [rsp+408h+var_3C4], eax
0x18007499f  mov     rax, [rsp+408h+var_3A0]
0x1800749a4  test    rax, rax
0x1800749a7  jnz     loc_180074C1C
0x1800749ad  mov     ecx, 360h
0x1800749b2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800749b8  mov     [rsp+408h+var_388], rax
0x1800749c0  test    rax, rax
0x1800749c3  jz      short loc_1800749D2
0x1800749c5  mov     rcx, rax; this
0x1800749c8  call    ??0CTimerNextFiringClass@@QEAA@XZ; CTimerNextFiringClass::CTimerNextFiringClass(void)
0x1800749cd  mov     rbx, rax
0x1800749d0  jmp     short loc_1800749D5
0x1800749d2  mov     rbx, rdi
0x1800749d5  test    rbx, rbx
0x1800749d8  jnz     short loc_180074A31
0x1800749da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800749e0  mov     ebx, 80041006h
0x1800749e5  mov     edx, ebx
0x1800749e7  mov     rcx, rax
0x1800749ea  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800749f0  lea     rax, WPP_GLOBAL_Control
0x1800749f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800749fe  cmp     rcx, rax
0x180074a01  jz      short loc_180074A2A
0x180074a03  test    byte ptr [rcx+1Ch], 1
0x180074a07  jz      short loc_180074A2A
0x180074a09  cmp     byte ptr [rcx+19h], 2
0x180074a0d  jb      short loc_180074A2A
0x180074a0f  mov     edx, 1Ch
0x180074a14  mov     r9d, 80041006h
0x180074a1a  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074a21  mov     rcx, [rcx+10h]
0x180074a25  call    WPP_SF_d
0x180074a2a  mov     eax, ebx
0x180074a2c  jmp     loc_1800752F9
0x180074a31  mov     [rsp+408h+var_380], rbx
0x180074a39  mov     rcx, rbx; this
0x180074a3c  call    ?Init@CIdentificationClass@@QEAAXXZ; CIdentificationClass::Init(void)
0x180074a41  mov     [rsp+408h+var_378], rdi
0x180074a49  lea     r8, [rsp+408h+var_378]
0x180074a51  lea     rdx, IID_IWbemClassObject
0x180074a58  mov     rcx, rbx
0x180074a5b  call    cs:__imp_?QueryInterface@CWbemObject@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWbemObject::QueryInterface(_GUID const &,void * *)
0x180074a61  mov     ebx, eax
0x180074a63  mov     [rsp+408h+var_3C4], eax
0x180074a67  test    eax, eax
0x180074a69  jns     short loc_180074AC8
0x180074a6b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074a71  mov     edx, ebx
0x180074a73  mov     rcx, rax
0x180074a76  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074a7c  lea     rax, WPP_GLOBAL_Control
0x180074a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180074a8a  cmp     rcx, rax
0x180074a8d  jz      short loc_180074AB4
0x180074a8f  test    byte ptr [rcx+1Ch], 1
0x180074a93  jz      short loc_180074AB4
0x180074a95  cmp     byte ptr [rcx+19h], 2
0x180074a99  jb      short loc_180074AB4
0x180074a9b  mov     edx, 1Dh
0x180074aa0  mov     r9d, ebx
0x180074aa3  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074aaa  mov     rcx, [rcx+10h]
0x180074aae  call    WPP_SF_d
0x180074ab3  nop
0x180074ab4  lea     rcx, [rsp+408h+var_380]
0x180074abc  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x180074ac1  mov     eax, ebx
0x180074ac3  jmp     loc_1800752F9
0x180074ac8  mov     rax, [rsp+408h+var_378]
0x180074ad0  mov     [rsp+408h+var_370], rax
0x180074ad8  mov     dword ptr [rsp+408h+phkResult], 1000h; unsigned int
0x180074ae0  mov     r9, [rsp+408h+var_378]; void *
0x180074ae8  mov     rdx, r15; struct IWmiDbHandle *
0x180074aeb  mov     rcx, r12; struct IWmiDbSession *
0x180074aee  call    ?PutObject@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@AEBU_GUID@@PEAXK@Z; CRepository::PutObject(IWmiDbSession *,IWmiDbHandle *,_GUID const &,void *,ulong)
0x180074af3  mov     ebx, eax
0x180074af5  mov     [rsp+408h+var_3C4], eax
0x180074af9  test    eax, eax
0x180074afb  jns     short loc_180074B68
0x180074afd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074b03  mov     edx, ebx
0x180074b05  mov     rcx, rax
0x180074b08  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074b0e  lea     rax, WPP_GLOBAL_Control
0x180074b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b1c  cmp     rcx, rax
0x180074b1f  jz      short loc_180074B46
0x180074b21  test    byte ptr [rcx+1Ch], 1
0x180074b25  jz      short loc_180074B46
0x180074b27  cmp     byte ptr [rcx+19h], 2
0x180074b2b  jb      short loc_180074B46
0x180074b2d  mov     edx, 1Eh
0x180074b32  mov     r9d, ebx
0x180074b35  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074b3c  mov     rcx, [rcx+10h]
0x180074b40  call    WPP_SF_d
0x180074b45  nop
0x180074b46  lea     rcx, [rsp+408h+var_370]; this
0x180074b4e  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074b53  nop
0x180074b54  lea     rcx, [rsp+408h+var_380]
0x180074b5c  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x180074b61  mov     eax, ebx
0x180074b63  jmp     loc_1800752F9
0x180074b68  lea     rax, [rsp+408h+var_3A0]
0x180074b6d  mov     [rsp+408h+phkResult], rax; struct IWbemClassObject **
0x180074b72  xor     r9d, r9d; unsigned int
0x180074b75  lea     r8, aCimomidentific_0; "__CIMOMIdentification"
0x180074b7c  mov     rdx, r15; struct IWmiDbHandle *
0x180074b7f  mov     rcx, r12; struct IWmiDbSession *
0x180074b82  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x180074b87  mov     ebx, eax
0x180074b89  mov     [rsp+408h+var_3C4], eax
0x180074b8d  test    eax, eax
0x180074b8f  jns     short loc_180074BFC
0x180074b91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074b97  mov     edx, ebx
0x180074b99  mov     rcx, rax
0x180074b9c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074ba2  lea     rax, WPP_GLOBAL_Control
0x180074ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180074bb0  cmp     rcx, rax
0x180074bb3  jz      short loc_180074BDA
0x180074bb5  test    byte ptr [rcx+1Ch], 1
0x180074bb9  jz      short loc_180074BDA
0x180074bbb  cmp     byte ptr [rcx+19h], 2
0x180074bbf  jb      short loc_180074BDA
0x180074bc1  mov     edx, 1Fh
0x180074bc6  mov     r9d, ebx
0x180074bc9  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074bd0  mov     rcx, [rcx+10h]
0x180074bd4  call    WPP_SF_d
0x180074bd9  nop
0x180074bda  lea     rcx, [rsp+408h+var_370]; this
0x180074be2  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074be7  nop
0x180074be8  lea     rcx, [rsp+408h+var_380]
0x180074bf0  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x180074bf5  mov     eax, ebx
0x180074bf7  jmp     loc_1800752F9
0x180074bfc  lea     rcx, [rsp+408h+var_370]; this
0x180074c04  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074c09  nop
0x180074c0a  lea     rcx, [rsp+408h+var_380]
0x180074c12  call    ??1?$CDeleteMe@VCSystemConfigClass@@@@QEAA@XZ; CDeleteMe<CSystemConfigClass>::~CDeleteMe<CSystemConfigClass>(void)
0x180074c17  mov     rax, [rsp+408h+var_3A0]
0x180074c1c  mov     [rsp+408h+var_388], rax
0x180074c24  mov     rcx, [rsp+408h+var_3A0]
0x180074c29  mov     rax, [rcx]
0x180074c2c  lea     r8, [rsp+408h+var_398]
0x180074c31  xor     edx, edx
0x180074c33  mov     rax, [rax+78h]
0x180074c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c3c  mov     ebx, eax
0x180074c3e  mov     [rsp+408h+var_3C4], eax
0x180074c42  test    eax, eax
0x180074c44  jns     short loc_180074CA3
0x180074c46  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074c4c  mov     edx, ebx
0x180074c4e  mov     rcx, rax
0x180074c51  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074c57  lea     rax, WPP_GLOBAL_Control
0x180074c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180074c65  cmp     rcx, rax
0x180074c68  jz      short loc_180074C8F
0x180074c6a  test    byte ptr [rcx+1Ch], 1
0x180074c6e  jz      short loc_180074C8F
0x180074c70  cmp     byte ptr [rcx+19h], 2
0x180074c74  jb      short loc_180074C8F
0x180074c76  mov     edx, 20h ; ' '
0x180074c7b  mov     r9d, ebx
0x180074c7e  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074c85  mov     rcx, [rcx+10h]
0x180074c89  call    WPP_SF_d
0x180074c8e  nop
0x180074c8f  lea     rcx, [rsp+408h+var_388]; this
0x180074c97  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074c9c  mov     eax, ebx
0x180074c9e  jmp     loc_1800752F9
0x180074ca3  lea     rcx, [rsp+408h+var_388]; this
0x180074cab  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074cb0  mov     r14, [rsp+408h+var_398]
0x180074cb5  mov     [rsp+408h+var_3B8], r14
0x180074cba  mov     r13, [rsp+408h+var_398]
0x180074cbf  xor     edx, edx; Val
0x180074cc1  mov     r8d, 20Ah; Size
0x180074cc7  lea     rcx, [rsp+408h+Data]; void *
0x180074ccf  call    memset_0
0x180074cd4  mov     [rsp+408h+hKey], rdi
0x180074cd9  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x180074cdf  test    al, al
0x180074ce1  jz      loc_180074D7F
0x180074ce7  call    cs:__imp_?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ; CWbemInstallObject::GetRegistryPathCIMOM(void)
0x180074ced  mov     rbx, rax
0x180074cf0  call    cs:__imp_?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ; CWbemInstallObject::GetRegistryPathRoot(void)
0x180074cf6  lea     rcx, [rsp+408h+hKey]
0x180074cfb  mov     [rsp+408h+phkResult], rcx; phkResult
0x180074d00  mov     r9d, 2000000h; samDesired
0x180074d06  xor     r8d, r8d; ulOptions
0x180074d09  mov     rdx, rbx; lpSubKey
0x180074d0c  mov     rcx, rax; hKey
0x180074d0f  call    cs:__imp_RegOpenKeyExW
0x180074d15  test    eax, eax
0x180074d17  jz      loc_180074E0C
0x180074d1d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074d23  mov     ebx, 80041001h
0x180074d28  mov     edx, ebx
0x180074d2a  mov     rcx, rax
0x180074d2d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074d33  lea     rax, WPP_GLOBAL_Control
0x180074d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d41  cmp     rcx, rax
0x180074d44  jz      short loc_180074D6E
0x180074d46  test    byte ptr [rcx+1Ch], 1
0x180074d4a  jz      short loc_180074D6E
0x180074d4c  cmp     byte ptr [rcx+19h], 2
0x180074d50  jb      short loc_180074D6E
0x180074d52  mov     edx, 21h ; '!'
0x180074d57  mov     r9d, 80041001h
0x180074d5d  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074d64  mov     rcx, [rcx+10h]
0x180074d68  call    WPP_SF_d
0x180074d6d  nop
0x180074d6e  lea     rcx, [rsp+408h+var_3B8]; this
0x180074d73  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074d78  mov     eax, ebx
0x180074d7a  jmp     loc_1800752F9
0x180074d7f  lea     rax, [rsp+408h+hKey]
0x180074d84  mov     [rsp+408h+phkResult], rax; phkResult
0x180074d89  mov     r9d, 2000000h; samDesired
0x180074d8f  xor     r8d, r8d; ulOptions
0x180074d92  lea     rdx, aSoftwareMicros_3; "software\\microsoft\\wbem\\cimom"
0x180074d99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180074da0  call    cs:__imp_RegOpenKeyExW
0x180074da6  test    eax, eax
0x180074da8  jz      short loc_180074E0C
0x180074daa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180074db0  mov     ebx, 80041001h
0x180074db5  mov     edx, ebx
0x180074db7  mov     rcx, rax
0x180074dba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180074dc0  lea     rax, WPP_GLOBAL_Control
0x180074dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180074dce  cmp     rcx, rax
0x180074dd1  jz      short loc_180074DFB
0x180074dd3  test    byte ptr [rcx+1Ch], 1
0x180074dd7  jz      short loc_180074DFB
0x180074dd9  cmp     byte ptr [rcx+19h], 2
0x180074ddd  jb      short loc_180074DFB
0x180074ddf  mov     edx, 22h ; '"'
0x180074de4  mov     r9d, 80041001h
0x180074dea  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x180074df1  mov     rcx, [rcx+10h]
0x180074df5  call    WPP_SF_d
0x180074dfa  nop
0x180074dfb  lea     rcx, [rsp+408h+var_3B8]; this
0x180074e00  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x180074e05  mov     eax, ebx
0x180074e07  jmp     loc_1800752F9
0x180074e0c  mov     rax, [rsp+408h+hKey]
0x180074e11  mov     [rsp+408h+var_388], rax
0x180074e19  mov     [rsp+408h+var_3B0], rax
0x180074e1e  xor     edx, edx; Val
  ... truncated ...
```
