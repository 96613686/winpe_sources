# CBlbBackupAsync::Initialize(CBlbEngine *,_GUID *,_GUID *,_BLBCAT_TEMPLATE_INFO *,ushort *,_BLB_CLIENT_LAUNCH_TYPE)

- ea: `0x1400290e4`
- end: `0x140029ceb`
- name: `?Initialize@CBlbBackupAsync@@QEAAJPEAVCBlbEngine@@PEAU_GUID@@1PEAU_BLBCAT_TEMPLATE_INFO@@PEAGW4_BLB_CLIENT_LAUNCH_TYPE@@@Z`
- size: `3079`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003fbf0`

## callees

- `0x140006948`
- `0x140006ca8`
- `0x140006d94`
- `0x140007ad3`
- `0x14000afd0`
- `0x14000b294`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x1400100d0`
- `0x140014200`
- `0x140014260`
- `0x140015148`
- `0x1400207e0`
- `0x140020a7c`
- `0x1400238ec`
- `0x1400290e4`
- `0x14002a994`
- `0x14002ae80`
- `0x14002bd34`
- `0x14002debc`
- `0x14003c54c`
- `0x14003c69c`
- `0x14004647c`
- `0x14007998c`
- `0x14008863c`
- `0x1400889f0`
- `0x14008f1b8`
- `0x14008fed0`
- `0x14009257c`
- `0x1400926d8`
- `0x1400f07dc`
- `0x1400f734c`
- `0x1400f7fa8`
- `0x1400f85a0`
- `0x1400fbedc`
- `0x1400fbfc0`
- `0x140100584`
- `0x14010158c`
- `0x1401061f8`
- `0x140112d4c`
- `0x1401218b8`
- `0x1401232b0`
- `0x140124d1c`
- `0x140127394`
- `0x14012e834`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x140029b0f`
- `KERNEL32!SystemTimeToFileTime` at `0x140029b0f`
- `KERNEL32!GetSystemTime` at `0x140029afe`
- `KERNEL32!GetSystemTime` at `0x140029afe`
- `KERNEL32!GetLastError` at `0x140029b19`
- `KERNEL32!GetLastError` at `0x140029b19`
- `ole32!CoTaskMemFree` at `0x140029c1e`
- `ole32!CoTaskMemFree` at `0x140029c51`
- `ole32!CoTaskMemFree` at `0x140029c1e`
- `ole32!CoTaskMemFree` at `0x140029c51`
- `OLEAUT32!__imp_SysFreeString` at `0x14002944a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002944a`

## string_xrefs

- `0x1400291ae`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400291cb`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400291e8`: `base\stor\blb\engine\service\backup.cpp`
- `0x140029205`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400294ee`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400291f9`: `pTemplCat`
- `0x1400294e2`: `pTemplCat->m_bSystemState == FALSE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBlbBackupAsync::Initialize(
        __int64 a1,
        struct CBlbEngine *a2,
        _OWORD *a3,
        _OWORD *a4,
        __int64 a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  unsigned __int16 **v11; // r13
  int ComputerName; // ebx
  char v13; // al
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  char v16; // al
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  CBlbBackupAsync *v19; // rcx
  unsigned int v20; // edx
  unsigned __int16 **v21; // rax
  const unsigned __int16 *v22; // rdx
  struct ATL::CComBSTR *v23; // rax
  CBlbBackupItemsHelper *v24; // r15
  unsigned int v25; // r12d
  unsigned int v26; // r14d
  CBlbApplicationBackupAsync **v27; // r14
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  CBlbSystemStateBackupAsync **v30; // r14
  unsigned int v31; // edx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int BackupFeatures; // eax
  __int64 v35; // rcx
  unsigned __int16 *v36; // r14
  int IsVolumeBitlocked; // eax
  int IsTargetValid; // eax
  _QWORD *v39; // rcx
  int v40; // edx
  int VolumeAccessPath; // eax
  unsigned int v42; // r9d
  char v43; // dl
  unsigned int i; // r8d
  signed int LastError; // eax
  unsigned int v46; // edx
  PVOID *v47; // rcx
  unsigned __int8 v49; // [rsp+40h] [rbp-A1h] BYREF
  unsigned __int8 v50[7]; // [rsp+41h] [rbp-A0h] BYREF
  struct _BLB_VOLUME_INFO *v51; // [rsp+48h] [rbp-99h] BYREF
  int v52; // [rsp+50h] [rbp-91h] BYREF
  unsigned int v53; // [rsp+54h] [rbp-8Dh] BYREF
  LPVOID pv; // [rsp+58h] [rbp-89h] BYREF
  BSTR bstrString[2]; // [rsp+60h] [rbp-81h] BYREF
  _OWORD v56[2]; // [rsp+70h] [rbp-71h] BYREF
  __int64 v57; // [rsp+90h] [rbp-51h]
  int v58; // [rsp+98h] [rbp-49h]
  int v59; // [rsp+A0h] [rbp-41h]
  __int64 v60; // [rsp+A8h] [rbp-39h]
  int v61; // [rsp+B0h] [rbp-31h]
  __int64 v62; // [rsp+B8h] [rbp-29h]
  char v63; // [rsp+C0h] [rbp-21h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-11h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  pv = 0;
  v50[0] = 0;
  v52 = 0;
  memset(v56, 0, sizeof(v56));
  v57 = 0;
  v58 = 10;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v59 = 0;
  v51 = 0;
  v53 = 0;
  v11 = 0;
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0xA95u, "pEngine");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0xA96u, "pguidSppGroupId");
  if ( !a4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0xA97u, "pguidBackupSetId");
  if ( !a5 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0xA98u, "pTemplCat");
  *(_DWORD *)(a1 + 232) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, a1);
  }
  ComputerName = CBlbAsync::Initialize((CBlbAsync *)(a1 + 24), a2, (unsigned __int8)a3);
  if ( ComputerName < 0 )
    goto LABEL_160;
  *(_OWORD *)(a1 + 280) = *a3;
  *(_OWORD *)(a1 + 296) = *a4;
  ComputerName = BlbutilDuplicateString(*(const unsigned __int16 **)(a5 + 16), (unsigned __int16 **)(a1 + 312), 0);
  if ( ComputerName < 0 )
    goto LABEL_160;
  ComputerName = BlbutilDuplicateString(a6, (unsigned __int16 **)(a1 + 608), 0);
  if ( ComputerName < 0 )
    goto LABEL_160;
  *(_WORD *)(a1 + 380) = *(_WORD *)(a5 + 96);
  *(_BYTE *)(a1 + 276) = *(_BYTE *)(a5 + 115);
  *(_DWORD *)(a1 + 384) = *(_DWORD *)(a5 + 116);
  v13 = *(_BYTE *)(a5 + 114);
  *(_BYTE *)(a1 + 388) = v13;
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = 113;
LABEL_29:
      WPP_SF_(v14[2], v15, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = 114;
      goto LABEL_29;
    }
  }
  v16 = *(_BYTE *)(a5 + 120);
  *(_BYTE *)(a1 + 390) = v16;
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = 115;
LABEL_39:
      WPP_SF_(v17[2], v18, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = 116;
      goto LABEL_39;
    }
  }
  *(_DWORD *)(a1 + 336) = *(_DWORD *)(a5 + 28);
  ComputerName = BlbutilGetComputerName((unsigned __int16 **)(a1 + 816));
  if ( ComputerName < 0 )
    goto LABEL_160;
  ComputerName = BlbutilDuplicateString(*(const unsigned __int16 **)(a5 + 72), (unsigned __int16 **)(a1 + 360), 0);
  if ( ComputerName < 0 )
    goto LABEL_160;
  v20 = *(_DWORD *)(a5 + 80);
  if ( v20 )
  {
    ComputerName = CBlbBackupAsync::PatchCatalogVolumeInfoWithCriticalVolumeInformation(
                     v19,
                     v20,
                     *(struct _BLBCAT_VOLUME_INFO **)(a5 + 88));
    if ( ComputerName < 0 )
      goto LABEL_160;
  }
  v21 = (unsigned __int16 **)operator new(0x20u);
  v11 = v21;
  bstrString[0] = (BSTR)v21;
  if ( !v21 )
  {
    v11 = 0;
    ComputerName = -2147024882;
    goto LABEL_160;
  }
  v21[1] = 0;
  *v21 = 0;
  v22 = *(const unsigned __int16 **)(a5 + 128);
  if ( v22 )
  {
    v23 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, v22);
    ComputerName = CBlbBackupItemsHelper::Initialize(v11, v23);
    SysFreeString(bstrString[0]);
    if ( ComputerName < 0 )
      goto LABEL_160;
    ComputerName = BlbutilDuplicateString(*(const unsigned __int16 **)(a5 + 128), (unsigned __int16 **)(a1 + 856), 0);
    if ( ComputerName < 0 )
      goto LABEL_160;
    v24 = (CBlbBackupItemsHelper *)v11;
  }
  else
  {
    v25 = *(_DWORD *)(a5 + 80);
    v53 = v25;
    ComputerName = BlbutilMemalloc((void **)&v51, v25, 0x80u);
    if ( ComputerName < 0 )
      goto LABEL_160;
    v26 = 0;
    v24 = (CBlbBackupItemsHelper *)v11;
    while ( v26 < v25 )
    {
      ComputerName = CBlbEngine::FillVolumeInfoFromCatalog(
                       (struct _GUID *)(*(_QWORD *)(a5 + 88) + 120LL * v26),
                       (struct _BLB_VOLUME_INFO *)((char *)v51 + 128 * (unsigned __int64)v26));
      if ( ComputerName < 0 )
        goto LABEL_160;
      ++v26;
    }
    if ( *(_BYTE *)(a5 + 120) )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0xB23u, "pTemplCat->m_bSystemState == FALSE");
    ComputerName = CBlbBackupItemsHelper::Initialize((CBlbBackupItemsHelper *)v11, v25, v51, 0, 0, 0, 1);
    if ( ComputerName < 0 )
      goto LABEL_160;
    ComputerName = CBlbBackupItemsHelper::GetBackupSpecsXML(
                     (CBlbBackupItemsHelper *)v11,
                     (unsigned __int16 **)(a1 + 856));
    if ( ComputerName < 0 )
      goto LABEL_160;
  }
  ComputerName = CBlbBackupItemsHelper::AreComponentsIncluded(v24, (unsigned __int8 *)(a1 + 391));
  if ( ComputerName < 0 )
    goto LABEL_160;
  v27 = (CBlbApplicationBackupAsync **)(a1 + 832);
  ComputerName = ATL::CComObject<CBlbApplicationBackupAsync>::CreateInstance(a1 + 832);
  if ( ComputerName < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 117;
LABEL_64:
      WPP_SF_d(v28[2], v29, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      goto LABEL_160;
    }
    goto LABEL_160;
  }
  (*(void (__fastcall **)(CBlbApplicationBackupAsync *))(*(_QWORD *)*v27 + 8LL))(*v27);
  ComputerName = CBlbApplicationBackupAsync::Initialize(*v27, (struct CBlbBackupAsync *)a1);
  if ( ComputerName < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 118;
      goto LABEL_64;
    }
    goto LABEL_160;
  }
  if ( *(_BYTE *)(a1 + 390) )
  {
    v30 = (CBlbSystemStateBackupAsync **)(a1 + 824);
    ComputerName = ATL::CComObject<CBlbSystemStateBackupAsync>::CreateInstance(a1 + 824);
    if ( ComputerName < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = 119;
        goto LABEL_64;
      }
      goto LABEL_160;
    }
    (*(void (__fastcall **)(CBlbSystemStateBackupAsync *))(*(_QWORD *)*v30 + 8LL))(*v30);
    ComputerName = CBlbSystemStateBackupAsync::Initialize(*v30, (struct CBlbBackupAsync *)a1);
    if ( ComputerName < 0 )
      goto LABEL_160;
  }
  v31 = *(_DWORD *)(a5 + 80);
  if ( v31 )
  {
    ComputerName = CBlbBackupAsync::InitializeVolumes(
                     a1,
                     v31,
                     *(_QWORD *)(a5 + 88),
                     *(_DWORD *)(a5 + 24),
                     *(_DWORD *)(a5 + 40),
                     *(_QWORD *)(a5 + 48),
                     (OLECHAR *)v24);
    if ( ComputerName < 0 )
      goto LABEL_160;
  }
  ComputerName = CBlbBackupItemsHelper::GetAllCriticalInfo(v24, (unsigned __int8 *)(a1 + 389));
  if ( ComputerName < 0 )
    goto LABEL_160;
  v49 = 0;
  ComputerName = CBlbBackupAsync::IsCreateNewBackupDirForSSB((CBlbBackupAsync *)a1, &v49);
  if ( ComputerName < 0 )
    goto LABEL_160;
  v33 = *(unsigned int *)(a1 + 336);
  if ( v49 )
  {
    LOBYTE(v32) = *(_BYTE *)(a1 + 390);
    BackupFeatures = BlbutilGetBackupFeatures(v33, v32);
  }
  else
  {
    BackupFeatures = BlbutilGetBackupFeatures(v33);
  }
  *(_DWORD *)(a1 + 340) = BackupFeatures;
  *(_OWORD *)bstrString = *(_OWORD *)a5;
  ComputerName = CBlbBackupAsync::InitializeTarget(
                   (CBlbBackupAsync *)a1,
                   (struct _GUID *)bstrString,
                   *(unsigned __int16 **)(a5 + 32),
                   *(_DWORD *)(a5 + 40),
                   *(struct _BLBCAT_TARGET_INFO **)(a5 + 48));
  if ( ComputerName < 0 )
    goto LABEL_160;
  v35 = *(unsigned int *)(a1 + 336);
  if ( (_DWORD)v35 != 4 )
  {
    if ( (BlbutilGetBackupFeatures(v35) & 0x200) == 0 )
    {
      v49 = 0;
      IsVolumeBitlocked = BlbIsVolumeBitlocked(*(unsigned __int16 **)(a1 + 344), &v49);
      if ( IsVolumeBitlocked >= 0 )
      {
        if ( v49 )
        {
          ComputerName = -2139619149;
          goto LABEL_160;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *(_QWORD *)(a1 + 344),
          IsVolumeBitlocked);
      }
    }
    ComputerName = BlbutilAppendString(*(const unsigned __int16 **)(a1 + 344), L"\\", (unsigned __int16 **)&pv);
    if ( ComputerName < 0 )
      goto LABEL_160;
    v36 = (unsigned __int16 *)pv;
    ComputerName = BlbIsVolumeNameValid((wchar_t *)pv, 0, v50);
    if ( ComputerName < 0 )
      goto LABEL_160;
    if ( !v50[0] )
    {
LABEL_105:
      ComputerName = -2139619316;
      goto LABEL_160;
    }
    IsTargetValid = BlbIsTargetValid(v36, v50, 0);
    ComputerName = IsTargetValid;
    if ( IsTargetValid >= 0 )
    {
      if ( !v50[0] )
        goto LABEL_105;
      IsTargetValid = BlbQueryVolumeMediaType(v36, (enum _BLB_MEDIA_TYPE *)&v52);
      ComputerName = IsTargetValid;
      if ( IsTargetValid >= 0 )
      {
        if ( v52 != *(_DWORD *)(a1 + 336) )
        {
          ComputerName = -2139619311;
          goto LABEL_160;
        }
        VolumeAccessPath = BlbQueryVolumeAccessPath(v36, (unsigned __int16 **)(a1 + 352));
        ComputerName = VolumeAccessPath;
        if ( VolumeAccessPath < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              VolumeAccessPath,
              (__int64)v36);
          }
          goto LABEL_160;
        }
        goto LABEL_89;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_160;
      }
      v40 = 122;
    }
    else
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_160;
      }
      v40 = 121;
    }
    WPP_SF_Sd(v39[2], v40, (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, (_DWORD)v36, IsTargetValid);
    goto LABEL_160;
  }
  ComputerName = CBlbAsync::CheckValidNetworkShareAndStoreImpersonationToken(
                   (CBlbAsync *)(a1 + 24),
                   *(unsigned __int16 **)(a1 + 344),
                   1u);
  if ( ComputerName < 0 )
    goto LABEL_160;
  ComputerName = BlbutilDuplicateString(*(const unsigned __int16 **)(a1 + 344), (unsigned __int16 **)(a1 + 352), 0);
  if ( ComputerName < 0 )
    goto LABEL_160;
  v36 = (unsigned __int16 *)pv;
LABEL_89:
  v49 = 0;
  ComputerName = BlbutilIsClientSKU(&v49);
  if ( ComputerName >= 0 )
  {
    if ( !v49 )
      goto LABEL_137;
    v42 = *(_DWORD *)(a1 + 368);
    if ( !v42 )
      goto LABEL_137;
    v43 = 0;
    for ( i = 0; i < v42; ++i )
    {
      if ( (*(_BYTE *)(368LL * i + *(_QWORD *)(a1 + 216) + 84) & 8) == 0 )
        v43 = 1;
    }
    if ( v43 )
    {
      ComputerName = -2139619001;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = 125;
        goto LABEL_64;
      }
    }
    else
    {
LABEL_137:
      if ( *(_DWORD *)(a1 + 320) == 1 && (unsigned int)(*(_DWORD *)(a1 + 336) - 2) <= 1 )
      {
        v49 = 0;
        ComputerName = CBlbVdsHelperLibrary::IsVolumeOnDynamicDisk((CBlbVdsHelperLibrary *)v56, v36, &v49);
        if ( ComputerName < 0 )
          goto LABEL_160;
        if ( v49
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v36);
        }
      }
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)(a1 + 392)) )
      {
        ComputerName = CBlbBackupAsync::EnumerateOnlineVHDFilePaths((CBlbBackupAsync *)a1);
        if ( ComputerName >= 0 )
        {
          memset_0((void *)(a1 + 864), 0, 0x88u);
          ComputerName = InitializeBackupSqmDatapoint(a1 + 864, a7, *(_QWORD *)(a1 + 344), a5, a1 + 40);
          if ( ComputerName < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            ComputerName = 0;
          }
        }
        else
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v29 = 127;
            goto LABEL_64;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        ComputerName = LastError;
        if ( LastError > 0 )
          ComputerName = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = 124;
      goto LABEL_64;
    }
  }
LABEL_160:
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(a1 + 40));
  if ( pv )
    CoTaskMemFree(pv);
  if ( v11 )
    CBlbBackupItemsHelper::`scalar deleting destructor'((CBlbBackupItemsHelper *)v11, v46);
  if ( v51 )
  {
    FreeVolumes(&v51, &v53);
    if ( v51 )
      CoTaskMemFree(v51);
  }
  if ( ComputerName >= 0 )
    goto LABEL_172;
  v47 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_177;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_172:
    v47 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v47 != &WPP_GLOBAL_Control && (*((_BYTE *)v47 + 28) & 1) != 0 && *((_BYTE *)v47 + 25) >= 4u )
    WPP_SF_(v47[2], 130, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_177:
  CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary((CBlbVdsHelperLibrary *)v56);
  return (unsigned int)ComputerName;
}

```

## disassembly

```asm
0x1400290e4  mov     [rsp-8+arg_10], rbx
0x1400290e9  push    rbp
0x1400290ea  push    rsi
0x1400290eb  push    rdi
0x1400290ec  push    r12
0x1400290ee  push    r13
0x1400290f0  push    r14
0x1400290f2  push    r15
0x1400290f4  lea     rbp, [rsp-0Fh]
0x1400290f9  sub     rsp, 0F0h
0x140029100  mov     rax, cs:__security_cookie
0x140029107  xor     rax, rsp
0x14002910a  mov     [rbp+3Fh+var_40], rax
0x14002910e  mov     r14, r9
0x140029111  mov     r15, r8
0x140029114  mov     rbx, rdx
0x140029117  mov     rdi, rcx
0x14002911a  mov     rsi, [rbp+3Fh+arg_20]
0x14002911e  mov     r12, [rbp+3Fh+arg_28]
0x140029122  lea     rax, WPP_GLOBAL_Control
0x140029129  mov     rcx, cs:WPP_GLOBAL_Control
0x140029130  cmp     rcx, rax
0x140029133  jz      short loc_140029156
0x140029135  test    byte ptr [rcx+1Ch], 1
0x140029139  jz      short loc_140029156
0x14002913b  cmp     byte ptr [rcx+19h], 4
0x14002913f  jb      short loc_140029156
0x140029141  mov     edx, 6Fh ; 'o'
0x140029146  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002914d  mov     rcx, [rcx+10h]
0x140029151  call    WPP_SF_
0x140029156  xor     eax, eax
0x140029158  mov     [rsp+120h+pv], rax
0x14002915d  mov     [rsp+120h+var_DF], al
0x140029161  mov     [rsp+120h+var_D0], eax
0x140029165  xorps   xmm0, xmm0
0x140029168  movdqa  [rbp+3Fh+var_B0], xmm0
0x14002916d  xorps   xmm1, xmm1
0x140029170  movdqa  [rbp+3Fh+var_A0], xmm1
0x140029175  mov     [rbp+3Fh+var_90], rax
0x140029179  mov     [rbp+3Fh+var_88], 0Ah
0x140029180  mov     [rbp+3Fh+var_78], rax
0x140029184  mov     [rbp+3Fh+var_70], eax
0x140029187  mov     [rbp+3Fh+var_68], rax
0x14002918b  mov     [rbp+3Fh+var_60], al
0x14002918e  mov     [rbp+3Fh+var_80], eax
0x140029191  mov     [rsp+120h+var_D8], rax
0x140029196  mov     [rsp+120h+var_CC], eax
0x14002919a  mov     r13d, eax
0x14002919d  test    rbx, rbx
0x1400291a0  jnz     short loc_1400291BA
0x1400291a2  lea     r8, aPengine; "pEngine"
0x1400291a9  mov     edx, 0A95h; unsigned int
0x1400291ae  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400291b5  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400291ba  test    r15, r15
0x1400291bd  jnz     short loc_1400291D7
0x1400291bf  lea     r8, aPguidsppgroupi; "pguidSppGroupId"
0x1400291c6  mov     edx, 0A96h; unsigned int
0x1400291cb  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400291d2  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400291d7  test    r14, r14
0x1400291da  jnz     short loc_1400291F4
0x1400291dc  lea     r8, aPguidbackupset; "pguidBackupSetId"
0x1400291e3  mov     edx, 0A97h; unsigned int
0x1400291e8  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400291ef  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400291f4  test    rsi, rsi
0x1400291f7  jnz     short loc_140029211
0x1400291f9  lea     r8, aPtemplcat; "pTemplCat"
0x140029200  mov     edx, 0A98h; unsigned int
0x140029205  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002920c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140029211  mov     dword ptr [rdi+0E8h], 1
0x14002921b  mov     rcx, cs:WPP_GLOBAL_Control
0x140029222  lea     rdx, WPP_GLOBAL_Control
0x140029229  cmp     rcx, rdx
0x14002922c  jz      short loc_140029252
0x14002922e  test    byte ptr [rcx+1Ch], 1
0x140029232  jz      short loc_140029252
0x140029234  cmp     byte ptr [rcx+19h], 4
0x140029238  jb      short loc_140029252
0x14002923a  mov     edx, 70h ; 'p'
0x14002923f  mov     r9, rdi
0x140029242  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140029249  mov     rcx, [rcx+10h]
0x14002924d  call    WPP_SF_q
0x140029252  lea     rcx, [rdi+18h]; this
0x140029256  mov     rdx, rbx; struct CBlbEngine *
0x140029259  call    ?Initialize@CBlbAsync@@QEAAJPEAVCBlbEngine@@E@Z; CBlbAsync::Initialize(CBlbEngine *,uchar)
0x14002925e  mov     ebx, eax
0x140029260  test    eax, eax
0x140029262  js      loc_140029BF1
0x140029268  movups  xmm0, xmmword ptr [r15]
0x14002926c  movdqu  xmmword ptr [rdi+118h], xmm0
0x140029274  movups  xmm1, xmmword ptr [r14]
0x140029278  movdqu  xmmword ptr [rdi+128h], xmm1
0x140029280  lea     rdx, [rdi+138h]; unsigned __int16 **
0x140029287  xor     r8d, r8d; unsigned __int64
0x14002928a  mov     rcx, [rsi+10h]; unsigned __int16 *
0x14002928e  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140029293  mov     ebx, eax
0x140029295  test    eax, eax
0x140029297  js      loc_140029BF1
0x14002929d  lea     rdx, [rdi+260h]; unsigned __int16 **
0x1400292a4  xor     r8d, r8d; unsigned __int64
0x1400292a7  mov     rcx, r12; unsigned __int16 *
0x1400292aa  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400292af  mov     ebx, eax
0x1400292b1  xor     r12d, r12d
0x1400292b4  test    eax, eax
0x1400292b6  js      loc_140029BFE
0x1400292bc  movzx   eax, word ptr [rsi+60h]
0x1400292c0  mov     [rdi+17Ch], ax
0x1400292c7  mov     al, [rsi+73h]
0x1400292ca  mov     [rdi+114h], al
0x1400292d0  mov     eax, [rsi+74h]
0x1400292d3  mov     [rdi+180h], eax
0x1400292d9  mov     al, [rsi+72h]
0x1400292dc  mov     [rdi+184h], al
0x1400292e2  test    al, al
0x1400292e4  jz      short loc_14002930C
0x1400292e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400292ed  lea     rdx, WPP_GLOBAL_Control
0x1400292f4  cmp     rcx, rdx
0x1400292f7  jz      short loc_140029347
0x1400292f9  test    byte ptr [rcx+1Ch], 1
0x1400292fd  jz      short loc_140029347
0x1400292ff  cmp     byte ptr [rcx+19h], 4
0x140029303  jb      short loc_140029347
0x140029305  lea     edx, [r12+71h]
0x14002930a  jmp     short loc_140029330
0x14002930c  mov     rcx, cs:WPP_GLOBAL_Control
0x140029313  lea     rdx, WPP_GLOBAL_Control
0x14002931a  cmp     rcx, rdx
0x14002931d  jz      short loc_140029347
0x14002931f  test    byte ptr [rcx+1Ch], 1
0x140029323  jz      short loc_140029347
0x140029325  cmp     byte ptr [rcx+19h], 4
0x140029329  jb      short loc_140029347
0x14002932b  mov     edx, 72h ; 'r'
0x140029330  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140029337  mov     rcx, [rcx+10h]
0x14002933b  call    WPP_SF_
0x140029340  lea     rdx, WPP_GLOBAL_Control
0x140029347  mov     al, [rsi+78h]
0x14002934a  mov     [rdi+186h], al
0x140029350  test    al, al
0x140029352  jz      short loc_140029373
0x140029354  mov     rcx, cs:WPP_GLOBAL_Control
0x14002935b  cmp     rcx, rdx
0x14002935e  jz      short loc_1400293A0
0x140029360  test    byte ptr [rcx+1Ch], 1
0x140029364  jz      short loc_1400293A0
0x140029366  cmp     byte ptr [rcx+19h], 4
0x14002936a  jb      short loc_1400293A0
0x14002936c  mov     edx, 73h ; 's'
0x140029371  jmp     short loc_140029390
0x140029373  mov     rcx, cs:WPP_GLOBAL_Control
0x14002937a  cmp     rcx, rdx
0x14002937d  jz      short loc_1400293A0
0x14002937f  test    byte ptr [rcx+1Ch], 1
0x140029383  jz      short loc_1400293A0
0x140029385  cmp     byte ptr [rcx+19h], 4
0x140029389  jb      short loc_1400293A0
0x14002938b  mov     edx, 74h ; 't'
0x140029390  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140029397  mov     rcx, [rcx+10h]
0x14002939b  call    WPP_SF_
0x1400293a0  mov     eax, [rsi+1Ch]
0x1400293a3  mov     [rdi+150h], eax
0x1400293a9  lea     rcx, [rdi+330h]; unsigned __int16 **
0x1400293b0  call    ?BlbutilGetComputerName@@YAJPEAPEAG@Z; BlbutilGetComputerName(ushort * *)
0x1400293b5  mov     ebx, eax
0x1400293b7  test    eax, eax
0x1400293b9  js      loc_140029BFE
0x1400293bf  lea     rdx, [rdi+168h]; unsigned __int16 **
0x1400293c6  xor     r8d, r8d; unsigned __int64
0x1400293c9  mov     rcx, [rsi+48h]; unsigned __int16 *
0x1400293cd  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400293d2  mov     ebx, eax
0x1400293d4  test    eax, eax
0x1400293d6  js      loc_140029BFE
0x1400293dc  mov     edx, [rsi+50h]; unsigned int
0x1400293df  test    edx, edx
0x1400293e1  jz      short loc_1400293F6
0x1400293e3  mov     r8, [rsi+58h]; struct _BLBCAT_VOLUME_INFO *
0x1400293e7  call    ?PatchCatalogVolumeInfoWithCriticalVolumeInformation@CBlbBackupAsync@@AEAAJKPEAU_BLBCAT_VOLUME_INFO@@@Z; CBlbBackupAsync::PatchCatalogVolumeInfoWithCriticalVolumeInformation(ulong,_BLBCAT_VOLUME_INFO *)
0x1400293ec  mov     ebx, eax
0x1400293ee  test    eax, eax
0x1400293f0  js      loc_140029BFE
0x1400293f6  mov     ecx, 20h ; ' '; Size
0x1400293fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140029400  mov     r13, rax
0x140029403  mov     [rsp+120h+bstrString], rax
0x140029408  test    rax, rax
0x14002940b  jz      loc_140029BF6
0x140029411  mov     [rax+8], r12
0x140029415  mov     [rax], r12
0x140029418  test    rax, rax
0x14002941b  jz      loc_140029BF9
0x140029421  mov     rdx, [rsi+80h]; unsigned __int16 *
0x140029428  test    rdx, rdx
0x14002942b  jz      short loc_140029480
0x14002942d  lea     rcx, [rsp+120h+bstrString]; this
0x140029432  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140029437  nop
0x140029438  mov     rdx, rax; struct ATL::CComBSTR *
0x14002943b  mov     rcx, r13; this
0x14002943e  call    ?Initialize@CBlbBackupItemsHelper@@QEAAJAEAVCComBSTR@ATL@@@Z; CBlbBackupItemsHelper::Initialize(ATL::CComBSTR &)
0x140029443  mov     ebx, eax
0x140029445  mov     rcx, [rsp+120h+bstrString]; bstrString
0x14002944a  call    cs:__imp_SysFreeString
0x140029450  test    ebx, ebx
0x140029452  js      loc_140029BFE
0x140029458  lea     rdx, [rdi+358h]; unsigned __int16 **
0x14002945f  xor     r8d, r8d; unsigned __int64
0x140029462  mov     rcx, [rsi+80h]; unsigned __int16 *
0x140029469  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14002946e  mov     ebx, eax
0x140029470  test    eax, eax
0x140029472  js      loc_140029BFE
0x140029478  mov     r15, r13
0x14002947b  jmp     loc_140029546
0x140029480  mov     r12d, [rsi+50h]
0x140029484  mov     [rsp+120h+var_CC], r12d
0x140029489  mov     r8d, 80h; unsigned int
0x14002948f  mov     edx, r12d; unsigned int
0x140029492  lea     rcx, [rsp+120h+var_D8]; void **
0x140029497  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14002949c  mov     ebx, eax
0x14002949e  test    eax, eax
0x1400294a0  js      loc_140029BF1
0x1400294a6  xor     r14d, r14d
0x1400294a9  mov     r15, r13
0x1400294ac  cmp     r14d, r12d
0x1400294af  jnb     short loc_1400294DC
0x1400294b1  mov     eax, r14d
0x1400294b4  mov     edx, r14d
0x1400294b7  shl     rdx, 7
0x1400294bb  add     rdx, [rsp+120h+var_D8]; struct _BLB_VOLUME_INFO *
0x1400294c0  imul    rcx, rax, 78h ; 'x'
0x1400294c4  add     rcx, [rsi+58h]; struct _GUID *
0x1400294c8  call    ?FillVolumeInfoFromCatalog@CBlbEngine@@SAJPEAU_BLBCAT_VOLUME_INFO@@PEAU_BLB_VOLUME_INFO@@@Z; CBlbEngine::FillVolumeInfoFromCatalog(_BLBCAT_VOLUME_INFO *,_BLB_VOLUME_INFO *)
0x1400294cd  mov     ebx, eax
0x1400294cf  test    eax, eax
0x1400294d1  js      loc_140029BF1
0x1400294d7  inc     r14d
0x1400294da  jmp     short loc_1400294AC
0x1400294dc  cmp     byte ptr [rsi+78h], 0
0x1400294e0  jz      short loc_1400294FA
0x1400294e2  lea     r8, aPtemplcatMBsys; "pTemplCat->m_bSystemState == FALSE"
0x1400294e9  mov     edx, 0B23h; unsigned int
0x1400294ee  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400294f5  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400294fa  mov     [rsp+120h+var_F0], 1; char
0x1400294ff  mov     [rsp+120h+var_F8], 0; char
0x140029504  mov     [rsp+120h+var_100], 0; struct _BLB_COMPONENT *
0x14002950d  xor     r9d, r9d; unsigned int
0x140029510  mov     r8, [rsp+120h+var_D8]; struct _BLB_VOLUME_INFO *
0x140029515  mov     edx, r12d; unsigned int
0x140029518  mov     rcx, r13; this
0x14002951b  call    ?Initialize@CBlbBackupItemsHelper@@QEAAJKPEAU_BLB_VOLUME_INFO@@KPEAU_BLB_COMPONENT@@EE@Z; CBlbBackupItemsHelper::Initialize(ulong,_BLB_VOLUME_INFO *,ulong,_BLB_COMPONENT *,uchar,uchar)
0x140029520  mov     ebx, eax
0x140029522  xor     r12d, r12d
0x140029525  test    eax, eax
0x140029527  js      loc_140029BFE
0x14002952d  lea     rdx, [rdi+358h]; unsigned __int16 **
0x140029534  mov     rcx, r13; this
0x140029537  call    ?GetBackupSpecsXML@CBlbBackupItemsHelper@@QEAAJPEAPEAG@Z; CBlbBackupItemsHelper::GetBackupSpecsXML(ushort * *)
0x14002953c  mov     ebx, eax
0x14002953e  test    eax, eax
0x140029540  js      loc_140029BFE
0x140029546  lea     rdx, [rdi+187h]; unsigned __int8 *
0x14002954d  mov     rcx, r15; this
0x140029550  call    ?AreComponentsIncluded@CBlbBackupItemsHelper@@QEAAJPEAE@Z; CBlbBackupItemsHelper::AreComponentsIncluded(uchar *)
0x140029555  mov     ebx, eax
0x140029557  test    eax, eax
0x140029559  js      loc_140029BFE
0x14002955f  lea     r14, [rdi+340h]
0x140029566  mov     rcx, r14
0x140029569  call    ?CreateInstance@?$CComObject@VCBlbApplicationBackupAsync@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBlbApplicationBackupAsync>::CreateInstance(ATL::CComObject<CBlbApplicationBackupAsync> * *)
0x14002956e  mov     ebx, eax
0x140029570  test    eax, eax
0x140029572  jns     short loc_1400295C1
0x140029574  mov     rcx, cs:WPP_GLOBAL_Control
0x14002957b  lea     rsi, WPP_GLOBAL_Control
0x140029582  mov     r15d, 1
0x140029588  cmp     rcx, rsi
0x14002958b  jz      loc_140029C0B
0x140029591  test    [rcx+1Ch], r15b
0x140029595  jz      loc_140029C0B
0x14002959b  cmp     byte ptr [rcx+19h], 2
0x14002959f  jb      loc_140029C0B
0x1400295a5  lea     edx, [r15+74h]
0x1400295a9  mov     r9d, eax
0x1400295ac  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400295b3  mov     rcx, [rcx+10h]
0x1400295b7  call    WPP_SF_d
0x1400295bc  jmp     loc_140029C0B
  ... truncated ...
```
