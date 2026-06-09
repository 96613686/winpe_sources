# CBlbRestoreComponentAsync::Initialize(CBlbEngine *,_GUID,_BLB_COMPONENT *,ulong,ushort *,ushort *,uchar,uchar,uchar,_BLB_CLIENT_LAUNCH_TYPE)

- ea: `0x14006c8b0`
- end: `0x14006d34f`
- name: `?Initialize@CBlbRestoreComponentAsync@@QEAAJPEAVCBlbEngine@@U_GUID@@PEAU_BLB_COMPONENT@@KPEAG3EEEW4_BLB_CLIENT_LAUNCH_TYPE@@@Z`
- size: `2719`
- prototype: `__int64 __fastcall(__int64, struct CBlbEngine *, struct _GUID *, struct _BLB_COMPONENT *, unsigned int, unsigned __int16 *, unsigned __int16 *, char, char, char, int)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400508d0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140006dd4`
- `0x140007654`
- `0x140007ad3`
- `0x14000b25c`
- `0x14000b294`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x1400142d8`
- `0x140014384`
- `0x14003c480`
- `0x14003c69c`
- `0x140043ec4`
- `0x140069d0c`
- `0x14006c26c`
- `0x14006c7fc`
- `0x14006c8b0`
- `0x14006dd70`
- `0x1400889f0`
- `0x14008a034`
- `0x14008f1b8`
- `0x140092a20`
- `0x1400ef92c`
- `0x1400f0f10`
- `0x140104e8c`
- `0x140106e60`
- `0x1401130e4`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x14006ce58`
- `KERNEL32!SystemTimeToFileTime` at `0x14006ce58`
- `KERNEL32!GetSystemTime` at `0x14006ce44`
- `KERNEL32!GetSystemTime` at `0x14006ce44`
- `KERNEL32!GetLastError` at `0x14006ce62`
- `KERNEL32!GetLastError` at `0x14006ce62`
- `msvcrt!_wcsicmp` at `0x14006ccb9`
- `msvcrt!_wcsicmp` at `0x14006ccb9`
- `ole32!CoTaskMemFree` at `0x14006caf0`
- `ole32!CoTaskMemFree` at `0x14006cb0c`
- `ole32!CoTaskMemFree` at `0x14006cb37`
- `ole32!CoTaskMemFree` at `0x14006cb89`
- `ole32!CoTaskMemFree` at `0x14006caf0`
- `ole32!CoTaskMemFree` at `0x14006cb0c`
- `ole32!CoTaskMemFree` at `0x14006cb37`
- `ole32!CoTaskMemFree` at `0x14006cb89`

## string_xrefs

- `0x14006c9bd`: `base\stor\blb\engine\service\component.cpp`
- `0x14006c9b1`: `m_bRecreatePath == TRUE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbRestoreComponentAsync::Initialize(
        __int64 a1,
        struct CBlbEngine *a2,
        struct _GUID *a3,
        struct _BLB_COMPONENT *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        char a8,
        char a9,
        char a10,
        int a11)
{
  unsigned __int8 v14; // r8
  struct IBLBCatalogSystem *Catalog; // r14
  signed int ComputerName; // r12d
  __int64 v17; // r9
  PVOID *v18; // rcx
  unsigned int v19; // r14d
  _QWORD *v20; // rax
  unsigned int v21; // esi
  __int64 v22; // rbx
  void *v23; // rcx
  void *v24; // rcx
  struct _BLB_COMPONENT *v26; // r14
  __int64 i; // rdi
  __int64 v28; // rdx
  wchar_t *v29; // rdi
  char v30; // r13
  signed int LastError; // eax
  int LoggingPaths; // eax
  struct _BLB_COMPONENT *v33; // r8
  __int64 v34; // rax
  bool v35; // cf
  unsigned __int64 v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rdi
  char v39; // r14
  char v40; // r15
  __int64 j; // rsi
  char *v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned int v51; // esi
  _DWORD *v52; // rax
  _DWORD *v53; // rdi
  unsigned __int8 v54; // [rsp+70h] [rbp-51h] BYREF
  char v55; // [rsp+71h] [rbp-50h]
  LPVOID pv; // [rsp+78h] [rbp-49h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp-41h] BYREF
  struct _BLB_COMPONENT *v58; // [rsp+88h] [rbp-39h]
  struct _GUID v59; // [rsp+90h] [rbp-31h] BYREF
  struct CBlbEngine *v60; // [rsp+A0h] [rbp-21h]
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-19h] BYREF

  v58 = a4;
  v60 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  Catalog = CBlbAsync::GetCatalog((CBlbAsync *)(a1 + 8));
  v54 = 0;
  pv = 0;
  String2 = 0;
  *(_DWORD *)(a1 + 204) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids, a1);
  }
  ComputerName = CBlbAsync::Initialize((CBlbAsync *)(a1 + 8), a2, v14);
  if ( ComputerName < 0 )
    goto LABEL_20;
  *(_BYTE *)(a1 + 594) = a10;
  if ( a7 )
  {
    if ( !a9 )
      goto LABEL_15;
    if ( a10 != 1 )
      BlbAssert("base\\stor\\blb\\engine\\service\\component.cpp", 0x6F5u, "m_bRecreatePath == TRUE");
  }
  *(_BYTE *)(a1 + 593) = 1;
LABEL_15:
  memset_0((void *)(a1 + 312), 0, 0xD0u);
  v59 = *a3;
  LOBYTE(v17) = 1;
  ComputerName = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, struct _GUID *, __int64, __int64))(*(_QWORD *)Catalog + 88LL))(
                   Catalog,
                   &v59,
                   a1 + 312,
                   v17);
  if ( ComputerName < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    WPP_SF_DDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
      a3->Data1,
      a3->Data2,
      a3->Data3,
      a3->Data4[0],
      a3->Data4[1],
      a3->Data4[2],
      a3->Data4[3],
      a3->Data4[4],
      a3->Data4[5],
      a3->Data4[6],
      a3->Data4[7]);
LABEL_20:
    v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
    v19 = a5;
    goto LABEL_22;
  }
  v26 = v58;
  ComputerName = BlbCheckComponentsInBackup(
                   v58,
                   a5,
                   *(struct _BLBCAT_COMPONENT_INFO **)(a1 + 400),
                   *(_DWORD *)(a1 + 392));
  if ( ComputerName < 0 )
    goto LABEL_20;
  for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
  {
    v59 = *(struct _GUID *)((char *)v26 + 72 * i + 16);
    BlbutilIsWriterComponentRestorable(
      (struct _BLBCAT_BACKUP_SET_INFO *)(a1 + 312),
      &v59,
      *((unsigned __int16 **)v26 + 9 * i),
      *((unsigned __int16 **)v26 + 9 * i + 1),
      &v54);
    if ( !v54 )
    {
      ComputerName = -2139619248;
      goto LABEL_20;
    }
  }
  ComputerName = BlbutilGetComputerName(&String2);
  if ( ComputerName < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = 74;
LABEL_56:
      WPP_SF_d(v18[2], v28, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_57;
  }
  v29 = String2;
  if ( _wcsicmp(*(const wchar_t **)(a1 + 464), String2) && !a7 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
        *(_QWORD *)(a1 + 464),
        (__int64)v29);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    ComputerName = -2139619161;
LABEL_57:
    v19 = a5;
    goto LABEL_22;
  }
  ComputerName = CBlbImpersonationHelper::CacheClientTokenIfNeeded((CBlbImpersonationHelper *)(a1 + 24));
  if ( ComputerName < 0 )
    goto LABEL_20;
  ComputerName = BlbQueryTargetMediaType(
                   a6,
                   (struct CBlbImpersonationHelper *)(a1 + 24),
                   (enum _BLB_MEDIA_TYPE *)(a1 + 528));
  if ( ComputerName < 0 )
  {
    CBlbImpersonationHelper::DiscardCachedCOMClientToken((CBlbImpersonationHelper *)(a1 + 24));
    goto LABEL_20;
  }
  if ( *(_DWORD *)(a1 + 528) != 4 )
    CBlbImpersonationHelper::DiscardCachedCOMClientToken((CBlbImpersonationHelper *)(a1 + 24));
  ComputerName = BlbGetTargetPathForBackupSet(
                   a6,
                   1u,
                   (struct _BLBCAT_BACKUP_SET_INFO *)(a1 + 312),
                   (struct CBlbImpersonationHelper *)(a1 + 24),
                   (unsigned __int16 **)(a1 + 288),
                   (unsigned __int16 **)(a1 + 296),
                   (unsigned __int16 **)(a1 + 304));
  if ( ComputerName < 0 )
    goto LABEL_20;
  *(struct _GUID *)(a1 + 208) = *a3;
  ComputerName = BlbutilDuplicateString(a6, (unsigned __int16 **)(a1 + 272), 0);
  v30 = 0;
  if ( ComputerName < 0 )
    goto LABEL_20;
  if ( a7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids, a7);
    }
    ComputerName = BlbutilDuplicateString(a7, (unsigned __int16 **)(a1 + 280), 0);
    if ( ComputerName < 0 )
      goto LABEL_20;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)(a1 + 520)) )
  {
    LastError = GetLastError();
    ComputerName = LastError;
    if ( LastError > 0 )
      ComputerName = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_20;
  }
  LoggingPaths = BlbutilGetLoggingPaths(
                   *(struct _FILETIME *)(a1 + 520),
                   L"ApplicationRestore",
                   L"ApplicationRestore_Error",
                   (unsigned __int16 **)(a1 + 536),
                   (unsigned __int16 **)(a1 + 544));
  ComputerName = LoggingPaths;
  if ( LoggingPaths < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      77,
      (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
      (unsigned int)L"ApplicationRestore",
      (__int64)L"ApplicationRestore_Error",
      LoggingPaths);
    goto LABEL_20;
  }
  if ( !*(_BYTE *)(a1 + 593) )
  {
    v19 = a5;
    goto LABEL_94;
  }
  v33 = v26;
  v19 = a5;
  ComputerName = CBlbRestoreComponentAsync::ReorderComponentsByApp(
                   (CBlbRestoreComponentAsync *)a1,
                   a5,
                   v33,
                   (struct _BLB_COMPONENT **)&pv);
  if ( ComputerName >= 0 )
  {
LABEL_94:
    *(_DWORD *)(a1 + 268) = v19;
    v34 = 232LL * v19;
    if ( !is_mul_ok(v19, 0xE8u) )
      v34 = -1;
    v35 = __CFADD__(v34, 8);
    v36 = v34 + 8;
    if ( v35 )
      v36 = -1;
    v37 = operator new[](v36);
    *(_QWORD *)&v59.Data1 = v37;
    if ( v37 )
    {
      *v37 = v19;
      v38 = v37 + 1;
      `eh vector constructor iterator'(
        v37 + 1,
        0xE8u,
        v19,
        ATL::CComObject<CBlbComponentRestoreContext>::`default constructor closure',
        (void (*)(void *))ATL::CComObject<CBlbComponentRestoreContext>::~CComObject<CBlbComponentRestoreContext>);
    }
    else
    {
      v38 = 0;
    }
    *(_QWORD *)(a1 + 224) = v38;
    if ( v38 )
    {
      v39 = 0;
      v40 = 0;
      v54 = 0;
      v55 = 0;
      for ( j = 0; (unsigned int)j < a5; j = (unsigned int)(j + 1) )
      {
        v42 = (char *)pv;
        if ( !*(_BYTE *)(a1 + 593) )
          v42 = (char *)v58;
        v43 = 232LL * (unsigned int)j;
        ComputerName = CBlbComponentRestoreContext::Initialize(
                         (CBlbComponentRestoreContext *)(v43 + *(_QWORD *)(a1 + 224)),
                         (struct _BLB_COMPONENT *)&v42[72 * j],
                         (struct CBlbRestoreComponentAsync *)a1);
        if ( ComputerName < 0 )
        {
          v18 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = 79;
            goto LABEL_56;
          }
          goto LABEL_57;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v43 + *(_QWORD *)(a1 + 224)) + 8LL))(v43 + *(_QWORD *)(a1 + 224));
        ComputerName = CBlbRestoreComponentAsync::AddToRestoreGroup((CBlbRestoreComponentAsync *)a1);
        if ( ComputerName < 0 )
          goto LABEL_20;
        v44 = *(_QWORD *)(a1 + 224);
        v45 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidClusterWriter.Data1;
        if ( !v45 )
          v45 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidClusterWriter.Data4;
        if ( v45 )
        {
          v46 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidADWriter.Data1;
          if ( !v46 )
            v46 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidADWriter.Data4;
          if ( v46 )
          {
            v47 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidDFSRWriter.Data1;
            if ( !v47 )
              v47 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidDFSRWriter.Data4;
            if ( !v47 )
              goto LABEL_123;
            v48 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidFRSWriter.Data1;
            if ( !v48 )
              v48 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidFRSWriter.Data4;
            if ( v48 )
            {
              v49 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidRegistryWriter.Data1;
              if ( !v49 )
                v49 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidRegistryWriter.Data4;
              if ( v49 )
              {
                v50 = *(_QWORD *)(v43 + v44 + 208) - *(_QWORD *)&g_guidHyperVWriter.Data1;
                if ( !v50 )
                  v50 = *(_QWORD *)(v43 + v44 + 216) - *(_QWORD *)g_guidHyperVWriter.Data4;
                if ( !v50 )
                  v39 = 1;
              }
              else
              {
                v30 = 1;
              }
            }
            else
            {
LABEL_123:
              v40 = 1;
            }
          }
          else
          {
            v54 = 1;
          }
        }
        else
        {
          v55 = 1;
        }
      }
      if ( v30 && v40 && v54 )
      {
        v51 = 5;
      }
      else if ( v55 )
      {
        v51 = 6;
      }
      else
      {
        v51 = 1;
        if ( v39 )
          v51 = 7;
      }
      ComputerName = CBlbRestoreComponentAsync::GetComponentListInRestoreOrder((CBlbRestoreComponentAsync *)a1);
      if ( ComputerName >= 0 )
      {
        v52 = operator new(0x48u);
        v53 = v52;
        *(_QWORD *)&v59.Data1 = v52;
        if ( v52 )
        {
          v52[2] = 0;
          *((_OWORD *)v52 + 1) = 0;
          *((_OWORD *)v52 + 2) = 0;
          *((_QWORD *)v52 + 6) = 0;
          *((_BYTE *)v52 + 56) = 0;
          *((_QWORD *)v52 + 8) = 0;
          *(_QWORD *)v52 = &ATL::CComObject<_BlbDummyCallback>::`vftable';
          (*(void (__fastcall **)(CBlbServiceModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
        }
        else
        {
          v53 = 0;
        }
        *(_QWORD *)(a1 + 552) = v53;
        if ( v53 )
        {
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v53 + 8LL))(v53);
          *(_QWORD *)(*(_QWORD *)(a1 + 552) + 64LL) = a1;
          *(_BYTE *)(a1 + 592) = a8;
          ComputerName = InitializeRecoverySqmDatapoint(
                           a1 + 596,
                           v60,
                           v51,
                           *(unsigned int *)(a1 + 528),
                           a11,
                           *(_QWORD *)(a1 + 272),
                           *(_QWORD *)(a1 + 412),
                           *(_QWORD *)(a1 + 520),
                           *(_QWORD *)(a1 + 280) != 0);
          if ( ComputerName >= 0 )
            *(_DWORD *)(a1 + 604) = *(_DWORD *)(a1 + 268);
        }
        else
        {
          ComputerName = -2147024882;
        }
        goto LABEL_20;
      }
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = 80;
        goto LABEL_56;
      }
      goto LABEL_57;
    }
    ComputerName = -2147024882;
    goto LABEL_92;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
LABEL_92:
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_22:
  v20 = pv;
  if ( pv )
  {
    v21 = 0;
    if ( v19 )
    {
      v22 = 0;
      do
      {
        v23 = (void *)v20[9 * v22 + 1];
        if ( v23 )
        {
          CoTaskMemFree(v23);
          *((_QWORD *)pv + 9 * v22 + 1) = 0;
          v20 = pv;
        }
        v24 = (void *)v20[9 * v22];
        if ( v24 )
        {
          CoTaskMemFree(v24);
          *((_QWORD *)pv + 9 * v22) = 0;
          v20 = pv;
        }
        ++v21;
        ++v22;
      }
      while ( v21 < v19 );
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v20 )
    {
      CoTaskMemFree(v20);
      pv = 0;
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( ComputerName < 0 && v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 2u )
  {
    WPP_SF_d(v18[2], 81, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( String2 )
  {
    CoTaskMemFree(String2);
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 4u )
    WPP_SF_(v18[2], 82, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  return (unsigned int)ComputerName;
}

```

## disassembly

```asm
0x14006c8b0  push    rbp
0x14006c8b2  push    rbx
0x14006c8b3  push    rsi
0x14006c8b4  push    rdi
0x14006c8b5  push    r12
0x14006c8b7  push    r13
0x14006c8b9  push    r14
0x14006c8bb  push    r15
0x14006c8bd  lea     rbp, [rsp-7]
0x14006c8c2  sub     rsp, 0C8h
0x14006c8c9  mov     rax, cs:__security_cookie
0x14006c8d0  xor     rax, rsp
0x14006c8d3  mov     [rbp+3Fh+var_48], rax
0x14006c8d7  mov     [rbp+3Fh+var_78], r9
0x14006c8db  mov     r13, r8
0x14006c8de  mov     r12, rdx
0x14006c8e1  mov     [rbp+3Fh+var_60], rdx
0x14006c8e5  mov     rbx, rcx
0x14006c8e8  mov     r15, [rbp+3Fh+arg_28]
0x14006c8ec  mov     rsi, [rbp+3Fh+arg_30]
0x14006c8f0  lea     rax, WPP_GLOBAL_Control
0x14006c8f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c8fe  cmp     rcx, rax
0x14006c901  jz      short loc_14006C924
0x14006c903  test    byte ptr [rcx+1Ch], 1
0x14006c907  jz      short loc_14006C924
0x14006c909  cmp     byte ptr [rcx+19h], 4
0x14006c90d  jb      short loc_14006C924
0x14006c90f  mov     edx, 47h ; 'G'
0x14006c914  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006c91b  mov     rcx, [rcx+10h]
0x14006c91f  call    WPP_SF_
0x14006c924  lea     rcx, [rbx+8]; this
0x14006c928  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x14006c92d  mov     r14, rax
0x14006c930  xor     eax, eax
0x14006c932  mov     [rbp+3Fh+var_90], al
0x14006c935  mov     [rbp+3Fh+pv], rax
0x14006c939  mov     [rbp+3Fh+String2], rax
0x14006c93d  mov     eax, 1
0x14006c942  mov     [rbx+0CCh], eax
0x14006c948  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c94f  lea     rdx, WPP_GLOBAL_Control
0x14006c956  cmp     rcx, rdx
0x14006c959  jz      short loc_14006C97C
0x14006c95b  test    [rcx+1Ch], al
0x14006c95e  jz      short loc_14006C97C
0x14006c960  cmp     byte ptr [rcx+19h], 4
0x14006c964  jb      short loc_14006C97C
0x14006c966  lea     edx, [rax+47h]
0x14006c969  mov     r9, rbx
0x14006c96c  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006c973  mov     rcx, [rcx+10h]
0x14006c977  call    WPP_SF_q
0x14006c97c  mov     rdx, r12; struct CBlbEngine *
0x14006c97f  lea     rcx, [rbx+8]; this
0x14006c983  call    ?Initialize@CBlbAsync@@QEAAJPEAVCBlbEngine@@E@Z; CBlbAsync::Initialize(CBlbEngine *,uchar)
0x14006c988  mov     r12d, eax
0x14006c98b  test    eax, eax
0x14006c98d  js      loc_14006CAB9
0x14006c993  mov     al, [rbp+3Fh+arg_48]
0x14006c999  mov     [rbx+252h], al
0x14006c99f  test    rsi, rsi
0x14006c9a2  jz      short loc_14006C9C9
0x14006c9a4  cmp     [rbp+3Fh+arg_40], 0
0x14006c9ab  jz      short loc_14006C9D0
0x14006c9ad  cmp     al, 1
0x14006c9af  jz      short loc_14006C9C9
0x14006c9b1  lea     r8, aMBrecreatepath; "m_bRecreatePath == TRUE"
0x14006c9b8  mov     edx, 6F5h; unsigned int
0x14006c9bd  lea     rcx, aBaseStorBlbEng_18; "base\\stor\\blb\\engine\\service\\compo"...
0x14006c9c4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14006c9c9  mov     byte ptr [rbx+251h], 1
0x14006c9d0  lea     rdi, [rbx+138h]
0x14006c9d7  xor     edx, edx; Val
0x14006c9d9  mov     r8d, 0D0h; Size
0x14006c9df  mov     rcx, rdi; void *
0x14006c9e2  call    memset_0
0x14006c9e7  movaps  xmm0, xmmword ptr [r13+0]
0x14006c9ec  movdqa  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x14006c9f1  mov     rax, [r14]
0x14006c9f4  mov     r9b, 1
0x14006c9f7  mov     r8, rdi
0x14006c9fa  lea     rdx, [rbp+3Fh+var_70]
0x14006c9fe  mov     rcx, r14
0x14006ca01  mov     rax, [rax+58h]
0x14006ca05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ca0a  mov     r12d, eax
0x14006ca0d  test    eax, eax
0x14006ca0f  jns     loc_14006CBDF
0x14006ca15  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ca1c  lea     rax, WPP_GLOBAL_Control
0x14006ca23  cmp     rcx, rax
0x14006ca26  jz      loc_14006CAC0
0x14006ca2c  test    byte ptr [rcx+1Ch], 1
0x14006ca30  jz      loc_14006CAC0
0x14006ca36  cmp     byte ptr [rcx+19h], 2
0x14006ca3a  jb      loc_14006CAC0
0x14006ca40  movzx   eax, byte ptr [r13+0Fh]
0x14006ca45  movzx   r8d, byte ptr [r13+0Eh]
0x14006ca4a  movzx   r9d, byte ptr [r13+0Dh]
0x14006ca4f  movzx   r10d, byte ptr [r13+0Ch]
0x14006ca54  movzx   r11d, byte ptr [r13+0Bh]
0x14006ca59  movzx   ebx, byte ptr [r13+0Ah]
0x14006ca5e  movzx   edi, byte ptr [r13+9]
0x14006ca63  movzx   esi, byte ptr [r13+8]
0x14006ca68  movzx   r14d, word ptr [r13+6]
0x14006ca6d  movzx   r15d, word ptr [r13+4]
0x14006ca72  mov     edx, 49h ; 'I'
0x14006ca77  mov     [rsp+100h+var_98], eax
0x14006ca7b  mov     [rsp+100h+var_A0], r8d
0x14006ca80  mov     [rsp+100h+var_A8], r9d
0x14006ca85  mov     [rsp+100h+var_B0], r10d
0x14006ca8a  mov     [rsp+100h+var_B8], r11d
0x14006ca8f  mov     [rsp+100h+var_C0], ebx
0x14006ca93  mov     dword ptr [rsp+100h+var_C8], edi
0x14006ca97  mov     dword ptr [rsp+100h+var_D0], esi
0x14006ca9b  mov     dword ptr [rsp+100h+var_D8], r14d
0x14006caa0  mov     dword ptr [rsp+100h+var_E0], r15d
0x14006caa5  mov     r9d, [r13+0]
0x14006caa9  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006cab0  mov     rcx, [rcx+10h]
0x14006cab4  call    WPP_SF_DDDDDDDDDDD
0x14006cab9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cac0  mov     r14d, [rbp+3Fh+arg_20]
0x14006cac4  lea     r13, WPP_GLOBAL_Control
0x14006cacb  mov     rax, [rbp+3Fh+pv]
0x14006cacf  xor     r15d, r15d
0x14006cad2  test    rax, rax
0x14006cad5  jz      short loc_14006CB48
0x14006cad7  mov     esi, r15d
0x14006cada  test    r14d, r14d
0x14006cadd  jz      short loc_14006CB2F
0x14006cadf  mov     ebx, r15d
0x14006cae2  lea     rdi, [rbx+rbx*8]
0x14006cae6  mov     rcx, [rax+rdi*8+8]; pv
0x14006caeb  test    rcx, rcx
0x14006caee  jz      short loc_14006CB03
0x14006caf0  call    cs:__imp_CoTaskMemFree
0x14006caf6  mov     rax, [rbp+3Fh+pv]
0x14006cafa  mov     [rax+rdi*8+8], r15
0x14006caff  mov     rax, [rbp+3Fh+pv]
0x14006cb03  mov     rcx, [rax+rdi*8]; pv
0x14006cb07  test    rcx, rcx
0x14006cb0a  jz      short loc_14006CB1E
0x14006cb0c  call    cs:__imp_CoTaskMemFree
0x14006cb12  mov     rax, [rbp+3Fh+pv]
0x14006cb16  mov     [rax+rdi*8], r15
0x14006cb1a  mov     rax, [rbp+3Fh+pv]
0x14006cb1e  inc     esi
0x14006cb20  inc     rbx
0x14006cb23  cmp     esi, r14d
0x14006cb26  jb      short loc_14006CAE2
0x14006cb28  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb2f  test    rax, rax
0x14006cb32  jz      short loc_14006CB48
0x14006cb34  mov     rcx, rax; pv
0x14006cb37  call    cs:__imp_CoTaskMemFree
0x14006cb3d  mov     [rbp+3Fh+pv], r15
0x14006cb41  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb48  test    r12d, r12d
0x14006cb4b  jns     short loc_14006CB7D
0x14006cb4d  cmp     rcx, r13
0x14006cb50  jz      short loc_14006CB7D
0x14006cb52  test    byte ptr [rcx+1Ch], 1
0x14006cb56  jz      short loc_14006CB7D
0x14006cb58  cmp     byte ptr [rcx+19h], 2
0x14006cb5c  jb      short loc_14006CB7D
0x14006cb5e  mov     edx, 51h ; 'Q'
0x14006cb63  mov     r9d, r12d
0x14006cb66  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006cb6d  mov     rcx, [rcx+10h]
0x14006cb71  call    WPP_SF_d
0x14006cb76  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb7d  mov     rax, [rbp+3Fh+String2]
0x14006cb81  test    rax, rax
0x14006cb84  jz      short loc_14006CB96
0x14006cb86  mov     rcx, rax; pv
0x14006cb89  call    cs:__imp_CoTaskMemFree
0x14006cb8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cb96  cmp     rcx, r13
0x14006cb99  jz      short loc_14006CBBC
0x14006cb9b  test    byte ptr [rcx+1Ch], 1
0x14006cb9f  jz      short loc_14006CBBC
0x14006cba1  cmp     byte ptr [rcx+19h], 4
0x14006cba5  jb      short loc_14006CBBC
0x14006cba7  mov     edx, 52h ; 'R'
0x14006cbac  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006cbb3  mov     rcx, [rcx+10h]
0x14006cbb7  call    WPP_SF_
0x14006cbbc  mov     eax, r12d
0x14006cbbf  mov     rcx, [rbp+3Fh+var_48]
0x14006cbc3  xor     rcx, rsp; StackCookie
0x14006cbc6  call    __security_check_cookie
0x14006cbcb  add     rsp, 0C8h
0x14006cbd2  pop     r15
0x14006cbd4  pop     r14
0x14006cbd6  pop     r13
0x14006cbd8  pop     r12
0x14006cbda  pop     rdi
0x14006cbdb  pop     rsi
0x14006cbdc  pop     rbx
0x14006cbdd  pop     rbp
0x14006cbde  retn
0x14006cbdf  mov     r9d, [rbx+188h]; unsigned int
0x14006cbe6  mov     r8, [rbx+190h]; struct _BLBCAT_COMPONENT_INFO *
0x14006cbed  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x14006cbf0  mov     r14, [rbp+3Fh+var_78]
0x14006cbf4  mov     rcx, r14; struct _BLB_COMPONENT *
0x14006cbf7  call    ?BlbCheckComponentsInBackup@@YAJPEAU_BLB_COMPONENT@@KPEAU_BLBCAT_COMPONENT_INFO@@K@Z; BlbCheckComponentsInBackup(_BLB_COMPONENT *,ulong,_BLBCAT_COMPONENT_INFO *,ulong)
0x14006cbfc  mov     r12d, eax
0x14006cbff  test    eax, eax
0x14006cc01  js      loc_14006CAB9
0x14006cc07  xor     edi, edi
0x14006cc09  cmp     edi, [rbp+3Fh+arg_20]
0x14006cc0c  jnb     short loc_14006CC54
0x14006cc0e  lea     r8, [rdi+rdi*8]
0x14006cc12  movups  xmm0, xmmword ptr [r14+r8*8+10h]
0x14006cc18  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x14006cc1d  lea     rax, [rbp+3Fh+var_90]
0x14006cc21  mov     [rsp+100h+var_E0], rax; unsigned __int8 *
0x14006cc26  mov     r9, [r14+r8*8+8]; unsigned __int16 *
0x14006cc2b  mov     r8, [r14+r8*8]; unsigned __int16 *
0x14006cc2f  lea     rdx, [rbp+3Fh+var_70]; struct _GUID
0x14006cc33  lea     rcx, [rbx+138h]; struct _BLBCAT_BACKUP_SET_INFO *
0x14006cc3a  call    ?BlbutilIsWriterComponentRestorable@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@U_GUID@@PEAG2PEAE@Z; BlbutilIsWriterComponentRestorable(_BLBCAT_BACKUP_SET_INFO *,_GUID,ushort *,ushort *,uchar *)
0x14006cc3f  cmp     [rbp+3Fh+var_90], 0
0x14006cc43  jz      short loc_14006CC49
0x14006cc45  inc     edi
0x14006cc47  jmp     short loc_14006CC09
0x14006cc49  mov     r12d, 80780050h
0x14006cc4f  jmp     loc_14006CAB9
0x14006cc54  lea     rcx, [rbp+3Fh+String2]; unsigned __int16 **
0x14006cc58  call    ?BlbutilGetComputerName@@YAJPEAPEAG@Z; BlbutilGetComputerName(ushort * *)
0x14006cc5d  mov     r12d, eax
0x14006cc60  test    eax, eax
0x14006cc62  jns     short loc_14006CCAB
0x14006cc64  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cc6b  lea     r13, WPP_GLOBAL_Control
0x14006cc72  cmp     rcx, r13
0x14006cc75  jz      short loc_14006CCA2
0x14006cc77  test    byte ptr [rcx+1Ch], 1
0x14006cc7b  jz      short loc_14006CCA2
0x14006cc7d  cmp     byte ptr [rcx+19h], 2
0x14006cc81  jb      short loc_14006CCA2
0x14006cc83  mov     edx, 4Ah ; 'J'
0x14006cc88  mov     r9d, eax
0x14006cc8b  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006cc92  mov     rcx, [rcx+10h]
0x14006cc96  call    WPP_SF_d
0x14006cc9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cca2  mov     r14d, [rbp+3Fh+arg_20]
0x14006cca6  jmp     loc_14006CACB
0x14006ccab  mov     rdi, [rbp+3Fh+String2]
0x14006ccaf  mov     rdx, rdi; String2
0x14006ccb2  mov     rcx, [rbx+1D0h]; String1
0x14006ccb9  call    cs:__imp__wcsicmp
0x14006ccbf  test    eax, eax
0x14006ccc1  jz      short loc_14006CD15
0x14006ccc3  test    rsi, rsi
0x14006ccc6  jnz     short loc_14006CD15
0x14006ccc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cccf  lea     r13, WPP_GLOBAL_Control
0x14006ccd6  cmp     rcx, r13
0x14006ccd9  jz      short loc_14006CD0D
0x14006ccdb  test    byte ptr [rcx+1Ch], 1
0x14006ccdf  jz      short loc_14006CD0D
0x14006cce1  cmp     byte ptr [rcx+19h], 2
0x14006cce5  jb      short loc_14006CD0D
0x14006cce7  lea     edx, [rsi+4Bh]
0x14006ccea  mov     [rsp+100h+var_E0], rdi
0x14006ccef  mov     r9, [rbx+1D0h]
0x14006ccf6  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006ccfd  mov     rcx, [rcx+10h]
0x14006cd01  call    WPP_SF_SS
0x14006cd06  mov     rcx, cs:WPP_GLOBAL_Control
0x14006cd0d  mov     r12d, 807800A7h
0x14006cd13  jmp     short loc_14006CCA2
0x14006cd15  lea     rdi, [rbx+18h]
0x14006cd19  mov     rcx, rdi; this
0x14006cd1c  call    ?CacheClientTokenIfNeeded@CBlbImpersonationHelper@@QEAAJXZ; CBlbImpersonationHelper::CacheClientTokenIfNeeded(void)
0x14006cd21  mov     r12d, eax
0x14006cd24  test    eax, eax
0x14006cd26  js      loc_14006CAB9
0x14006cd2c  lea     r8, [rbx+210h]; enum _BLB_MEDIA_TYPE *
0x14006cd33  mov     rdx, rdi; this
0x14006cd36  mov     rcx, r15; unsigned __int16 *
0x14006cd39  call    ?BlbQueryTargetMediaType@@YAJPEAGPEAVCBlbImpersonationHelper@@PEAW4_BLB_MEDIA_TYPE@@@Z; BlbQueryTargetMediaType(ushort *,CBlbImpersonationHelper *,_BLB_MEDIA_TYPE *)
0x14006cd3e  mov     r12d, eax
0x14006cd41  test    eax, eax
0x14006cd43  jns     short loc_14006CD52
0x14006cd45  mov     rcx, rdi; this
0x14006cd48  call    ?DiscardCachedCOMClientToken@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::DiscardCachedCOMClientToken(void)
0x14006cd4d  jmp     loc_14006CAB9
0x14006cd52  cmp     dword ptr [rbx+210h], 4
0x14006cd59  jz      short loc_14006CD63
0x14006cd5b  mov     rcx, rdi; this
0x14006cd5e  call    ?DiscardCachedCOMClientToken@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::DiscardCachedCOMClientToken(void)
0x14006cd63  lea     rax, [rbx+130h]
0x14006cd6a  lea     rcx, [rbx+128h]
  ... truncated ...
```
