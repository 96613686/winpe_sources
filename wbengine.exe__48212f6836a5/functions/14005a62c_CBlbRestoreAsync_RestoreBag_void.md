# CBlbRestoreAsync::RestoreBag(void)

- ea: `0x14005a62c`
- end: `0x14005b4cf`
- name: `?RestoreBag@CBlbRestoreAsync@@AEAAJXZ`
- size: `3747`
- prototype: `__int64 __fastcall(CBlbRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400563a0`

## callees

- `0x1400020d0`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140026c8c`
- `0x14002cbe8`
- `0x14003cb70`
- `0x140057de0`
- `0x140058038`
- `0x14005a3b8`
- `0x14005a62c`
- `0x14005b564`
- `0x14005b5d0`
- `0x14005b8b0`
- `0x14005b944`
- `0x14005baa4`
- `0x14005c248`
- `0x140088ba4`
- `0x14008b58c`
- `0x140098c04`
- `0x1400be8b0`
- `0x1400bf240`
- `0x1400bf788`
- `0x1400bf9a4`
- `0x1400c0460`
- `0x1400c0734`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f222c`
- `0x1400f4188`
- `0x1400f4400`
- `0x140101124`
- `0x140102128`
- `0x140104148`
- `0x1401087ac`
- `0x14010a688`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14005a9e9`
- `KERNEL32!GetTickCount` at `0x14005ab90`
- `KERNEL32!GetTickCount` at `0x14005ac62`
- `KERNEL32!GetTickCount` at `0x14005ad44`
- `KERNEL32!GetTickCount` at `0x14005a9e9`
- `KERNEL32!GetTickCount` at `0x14005ab90`
- `KERNEL32!GetTickCount` at `0x14005ac62`
- `KERNEL32!GetTickCount` at `0x14005ad44`
- `ole32!CoTaskMemFree` at `0x14005b2dd`
- `ole32!CoTaskMemFree` at `0x14005b419`
- `ole32!CoTaskMemFree` at `0x14005b432`
- `ole32!CoTaskMemFree` at `0x14005b447`
- `ole32!CoTaskMemFree` at `0x14005b460`
- `ole32!CoTaskMemFree` at `0x14005b2dd`
- `ole32!CoTaskMemFree` at `0x14005b419`
- `ole32!CoTaskMemFree` at `0x14005b432`
- `ole32!CoTaskMemFree` at `0x14005b447`
- `ole32!CoTaskMemFree` at `0x14005b460`

## string_xrefs

- `0x14005a796`: `wszVhdExtension != NULL`
- `0x14005a728`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005a7a2`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005aa94`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005ae00`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005af4b`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005b022`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005b282`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005b31c`: `base\stor\blb\engine\service\restore.cpp`
- `0x14005aa88`: `wszMountedVhdPath != NULL`

## pseudocode

```c
__int64 __fastcall CBlbRestoreAsync::RestoreBag(CBlbRestoreAsync *this)
{
  __int64 v2; // rax
  WCHAR *v3; // r14
  CBlbAsync *v4; // r12
  struct IBLBCatalogSystem *Catalog; // rbx
  __int64 v6; // r9
  __int64 (__fastcall *v7)(struct IBLBCatalogSystem *, __int64 *, _BYTE *, __int64); // rax
  int AppropriateVhdExtension; // edi
  const unsigned __int16 *v9; // r12
  CBlbVolumeRestoreContext *v10; // r15
  bool v11; // r12
  __int64 v12; // rdx
  PCWSTR v13; // rbx
  int v14; // eax
  __int64 v15; // r8
  int v16; // ebx
  int v17; // r15d
  unsigned int IsBadClusInfoResetNeeded; // ebx
  PVOID *v19; // rcx
  int v20; // edx
  int v21; // r9d
  const WCHAR *v22; // rbx
  DWORD TickCount; // r15d
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  LPVOID v28; // r10
  unsigned int v29; // eax
  DWORD v30; // r15d
  void *v31; // rcx
  unsigned int v32; // eax
  void **v33; // r13
  void *ImpersonationToken; // rax
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // rax
  PVOID *v38; // rbx
  __int64 v39; // rax
  const unsigned __int16 *v40; // rcx
  int v41; // eax
  unsigned __int16 *v42; // r15
  __int64 v43; // r8
  unsigned __int8 v44; // bl
  const wchar_t *v45; // r9
  unsigned int v46; // r8d
  int v47; // eax
  unsigned __int16 *v48; // rcx
  int v49; // eax
  int (*v50)(unsigned __int16 *, unsigned __int16 *, struct _FILETIME); // r8
  int v51; // eax
  void *v52; // rcx
  PVOID *v53; // rcx
  const wchar_t *v54; // r9
  unsigned __int8 v56[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v57; // [rsp+74h] [rbp-8Ch] BYREF
  char v58; // [rsp+78h] [rbp-88h]
  CBlbVolumeRestoreContext *v59; // [rsp+80h] [rbp-80h]
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp-70h] BYREF
  int v62; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR v63; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpszVolumeName; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v66; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v67[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v68[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v69[192]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v70; // [rsp+1B0h] [rbp+B0h]
  unsigned int v71; // [rsp+1B4h] [rbp+B4h]
  __int64 v72; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v73; // [rsp+1C8h] [rbp+C8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  v2 = *((unsigned int *)this + 68);
  v62 = 0;
  lpszVolumeName = 0;
  v3 = 0;
  lpFileName = 0;
  v63 = 0;
  v59 = (CBlbVolumeRestoreContext *)(*((_QWORD *)this + 33) + 192 * v2);
  v57 = 0;
  v65 = 0;
  v66 = 0;
  pv = 0;
  v56[0] = 0;
  v58 = 0;
  memset(v67, 0, 24);
  v72 = 0;
  v73 = 0;
  memset_0(v69, 0, 0xD0u);
  v4 = (CBlbRestoreAsync *)((char *)this + 8);
  Catalog = CBlbAsync::GetCatalog((CBlbRestoreAsync *)((char *)this + 8));
  if ( !Catalog )
    BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x8B5u, "pCatalogSystem");
  LOBYTE(v6) = 1;
  v7 = *(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int64 *, _BYTE *, __int64))(*(_QWORD *)Catalog + 88LL);
  *(_OWORD *)v68 = *((_OWORD *)this + 13);
  AppropriateVhdExtension = v7(Catalog, v68, v69, v6);
  if ( AppropriateVhdExtension < 0 )
    goto LABEL_91;
  v58 = 1;
  AppropriateVhdExtension = BlbGetAppropriateVhdExtension(v70, v71, v67, v56);
  if ( AppropriateVhdExtension < 0 )
    goto LABEL_91;
  v9 = v67[0];
  if ( !v67[0] )
    BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x8C7u, "wszVhdExtension != NULL");
  v10 = v59;
  AppropriateVhdExtension = CBlbVolumeRestoreContext::GetRestoreTargetPath(v59, (unsigned __int16 **)&lpszVolumeName);
  if ( AppropriateVhdExtension < 0 )
    goto LABEL_158;
  AppropriateVhdExtension = BlbAppendBagFile(
                              *((unsigned __int16 **)this + 25),
                              (UUID *)((char *)v10 + 60),
                              *((_DWORD *)v10 + 19),
                              v9,
                              (unsigned __int16 **)&v63);
  if ( AppropriateVhdExtension < 0 )
    goto LABEL_158;
  v11 = 0;
  if ( (*((_BYTE *)v10 + 76) & 8) != 0 )
    v11 = (*((_BYTE *)v10 + 76) & 0x20) == 0;
  AppropriateVhdExtension = CBlbImpersonationHelper::ImpersonateCaller((CBlbRestoreAsync *)((char *)this + 24), 0);
  if ( AppropriateVhdExtension < 0 )
  {
LABEL_158:
    v3 = (WCHAR *)lpszVolumeName;
    goto LABEL_159;
  }
  v13 = v63;
  v14 = BlbVerifyFileNotCompressedOrEncrypted(v63, v12, 0);
  AppropriateVhdExtension = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        (_DWORD)v13,
        v14);
    }
    v3 = (WCHAR *)lpszVolumeName;
    goto LABEL_159;
  }
  CBlbImpersonationHelper::Revert((CBlbRestoreAsync *)((char *)this + 24));
  LOBYTE(v15) = 1;
  CBlbRestoreAsync::SetState(this, 3, v15);
  v3 = (WCHAR *)lpszVolumeName;
  AppropriateVhdExtension = BlbutilRemoveTrailingBackslash(lpszVolumeName, (unsigned __int16 **)&lpFileName);
  if ( AppropriateVhdExtension < 0 )
  {
LABEL_159:
    v4 = (CBlbRestoreAsync *)((char *)this + 8);
    goto LABEL_160;
  }
  if ( *((_QWORD *)this + 43) )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v16 = *((_DWORD *)v10 + 19) & 2;
    CBlbRestoreAsync::UpdateBytes(this, 0, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        (_DWORD)v3,
        *((_DWORD *)this + 68));
    }
    if ( !v16 )
    {
      AppropriateVhdExtension = CBlbRestoreAsync::HandleBitLockerBeforeRestore(this);
      if ( AppropriateVhdExtension < 0 )
        goto LABEL_159;
    }
    v17 = (int)lpFileName;
    IsBadClusInfoResetNeeded = BlbimgRecordRecoveryTargetBadClusExtents(lpFileName);
    if ( IsBadClusInfoResetNeeded )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v20 = 86;
      v21 = v17;
LABEL_35:
      WPP_SF_SLd(
        (unsigned int)v19[2],
        v20,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        v21,
        IsBadClusInfoResetNeeded,
        v57);
LABEL_36:
      AppropriateVhdExtension = BlbTranslateBlbimgError(IsBadClusInfoResetNeeded, v57, &v62);
LABEL_37:
      v10 = v59;
      goto LABEL_159;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v22 = v63;
    }
    else
    {
      v22 = v63;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          v17,
          (__int64)v63);
    }
    TickCount = GetTickCount();
    if ( (*((_BYTE *)this + 328) & 2) != 0 || v56[0] )
    {
      CBlbImpersonationHelper::GetImpersonationToken((CBlbRestoreAsync *)((char *)this + 24));
      v29 = BlbimgPrepareForRestore(lpFileName, (__int64)this + 344, (__int64)&v57);
    }
    else
    {
      v24 = CBlbVhdHelper::MountVolume((CBlbRestoreAsync *)((char *)this + 24), v22, 0, 0, 0, (unsigned __int16 **)&pv);
      AppropriateVhdExtension = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            88,
            (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
            (_DWORD)pv,
            v24);
        }
        goto LABEL_37;
      }
      v28 = pv;
      if ( !pv )
      {
        BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x93Fu, "wszMountedVhdPath != NULL");
        v28 = pv;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)v22,
          (__int64)v28);
        LODWORD(v28) = (_DWORD)pv;
      }
      LOBYTE(v26) = *((_BYTE *)this + 353);
      LOBYTE(v27) = 1;
      LOBYTE(v25) = *((_BYTE *)this + 352);
      v29 = BlbimgPrepareForReplication(
              (_DWORD)v28,
              v25,
              v26,
              v27,
              (__int64)BlbDeleteOmittedFilesCallback,
              (__int64)this);
    }
    IsBadClusInfoResetNeeded = v29;
    *((_DWORD *)this + 91) += GetTickCount() - TickCount;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( IsBadClusInfoResetNeeded )
    {
      if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 1) == 0 || *((_BYTE *)v19 + 25) < 2u )
        goto LABEL_36;
      v20 = 91;
      goto LABEL_67;
    }
    v13 = v63;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
    WPP_SF_SS(
      (unsigned int)v19[2],
      92,
      (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
      (_DWORD)lpFileName,
      (__int64)v13);
  v30 = GetTickCount();
  if ( (*((_BYTE *)this + 328) & 2) != 0 || v56[0] )
  {
    ImpersonationToken = CBlbImpersonationHelper::GetImpersonationToken((CBlbRestoreAsync *)((char *)this + 24));
    v33 = (void **)((char *)this + 344);
    v32 = BlbimgRestoreBackup(
            *((void **)this + 43),
            (__int64)ImpersonationToken,
            (__int64)&v72,
            (__int64)&v65,
            (__int64)&v66,
            (__int64)&v57);
  }
  else
  {
    v31 = (void *)*((_QWORD *)this + 43);
    *(GUID *)v68 = GUID_NULL;
    v32 = BlbimgPerformReplication(
            v31,
            0,
            (__int64)v68,
            0,
            0,
            (__int64)&v72,
            (__int64)&v65,
            (__int64)&v66,
            0,
            (__int64)&v57);
    v33 = (void **)((char *)this + 344);
  }
  IsBadClusInfoResetNeeded = v32;
  *((_DWORD *)this + 92) += GetTickCount() - v30;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  CBlbRestoreAsync::UpdateBytes(this, v66, v65);
  if ( IsBadClusInfoResetNeeded )
  {
    if ( IsBadClusInfoResetNeeded != 1 )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v20 = 94;
      goto LABEL_67;
    }
    v4 = (CBlbRestoreAsync *)((char *)this + 8);
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 16LL))((char *)this + 8) )
      BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x991u, "IsAborted()");
    AppropriateVhdExtension = -2139618969;
LABEL_91:
    v10 = v59;
    goto LABEL_160;
  }
  v35 = *((_QWORD *)this + 36);
  v36 = 108LL * *((unsigned int *)this + 70);
  v37 = v72 - *(_QWORD *)(v36 + v35 + 80);
  if ( v72 == *(_QWORD *)(v36 + v35 + 80) )
    v37 = v73 - *(_QWORD *)(v36 + v35 + 88);
  if ( !v37 || !v11 )
    goto LABEL_100;
  v38 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_DDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
      *(unsigned int *)(v36 + v35 + 80),
      *(_DWORD *)(v36 + v35 + 84),
      *(_DWORD *)(v36 + v35 + 88),
      *(_DWORD *)(v36 + v35 + 92),
      v72,
      HIDWORD(v72),
      v73,
      HIDWORD(v73));
LABEL_100:
    v38 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = v59;
  v39 = (unsigned int)(*((_DWORD *)this + 70) + 1);
  if ( (_DWORD)v39 == *((_DWORD *)this + 71)
    || !BlbutilIsVolumeMatch(
          (struct _GUID *)(108 * v39 + *((_QWORD *)this + 36) + 44LL),
          *(_DWORD *)(108 * v39 + *((_QWORD *)this + 36) + 60),
          (struct _GUID *)((char *)v59 + 60),
          *((_DWORD *)v59 + 19)) )
  {
    if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 && *((_BYTE *)v38 + 25) >= 4u )
      WPP_SF_Sd(
        (unsigned int)v38[2],
        96,
        (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
        (_DWORD)v3,
        *((_DWORD *)this + 68));
    if ( (*((_BYTE *)this + 328) & 2) != 0 || v56[0] )
      CBlbVolumeRestoreContext::SetBadClusterStat(v10, *v33);
    if ( !*v33 )
      BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0x9C5u, "m_pCurrentRestoreContext");
    BlbimgFreeContext(*v33);
    *v33 = 0;
    if ( (*((_BYTE *)v10 + 76) & 1) != 0 )
    {
      CBlbVolumeRestoreContext::SetState(v10, 9);
    }
    else
    {
      if ( *((_BYTE *)this + 384) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
        }
        v42 = (unsigned __int16 *)lpFileName;
      }
      else
      {
        v56[0] = 0;
        v42 = (unsigned __int16 *)lpFileName;
        IsBadClusInfoResetNeeded = BlbimgIsBadClusInfoResetNeeded(lpFileName);
        if ( IsBadClusInfoResetNeeded )
        {
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v20 = 97;
LABEL_67:
          v21 = (int)v3;
          goto LABEL_35;
        }
        v44 = v56[0];
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v45 = &String1;
          if ( !v56[0] )
            v45 = L"NOT";
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
            (_DWORD)v45,
            (__int64)v42);
        }
        if ( v44 )
        {
          LOBYTE(v43) = 1;
          CBlbRestoreAsync::SetState(this, 12, v43);
          AppropriateVhdExtension = CBlbVolumeRestoreContext::ResetBadClusterInfo(v59, v42, v46);
          if ( AppropriateVhdExtension < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
            }
            goto LABEL_37;
          }
        }
      }
      v47 = BlbExtendFileSystemToVolumeSize(v42);
      AppropriateVhdExtension = v47;
      if ( v47 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
            (_DWORD)v42,
            v47);
        }
        AppropriateVhdExtension = -2139619036;
        goto LABEL_37;
      }
      v10 = v59;
    }
    v4 = (CBlbRestoreAsync *)((char *)this + 8);
    CBlbAsync::LockedIncrement((CBlbRestoreAsync *)((char *)this + 8), (unsigned int *)this + 84);
  }
  else
  {
    v4 = (CBlbRestoreAsync *)((char *)this + 8);
  }
  CBlbAsync::LockedIncrement(v4, (unsigned int *)v10 + 4);
  v40 = (const unsigned __int16 *)pv;
  if ( !pv )
    goto LABEL_172;
  if ( (*((_BYTE *)this + 328) & 2) != 0 )
  {
    BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xA13u, "!CHUNKED(m_ulFeatures)");
    v40 = (const unsigned __int16 *)pv;
  }
  v41 = CBlbVhdHelper::Dismount(v40);
  AppropriateVhdExtension = v41;
  if ( v41 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids, pv);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
      (_DWORD)pv,
      v41);
  }
LABEL_160:
  v48 = (unsigned __int16 *)pv;
  if ( pv )
  {
    if ( (*((_BYTE *)this + 328) & 2) != 0 )
    {
      BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xA25u, "!CHUNKED(m_ulFeatures)");
      v48 = (unsigned __int16 *)pv;
    }
    if ( AppropriateVhdExtension < 0 )
    {
      v49 = CBlbVhdHelper::Dismount(v48);
      if ( v49 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)pv,
          v49);
      }
      v48 = (unsigned __int16 *)pv;
    }
    if ( v48 )
    {
      CoTaskMemFree(v48);
      pv = 0;
    }
  }
LABEL_172:
  CBlbImpersonationHelper::Revert((CBlbRestoreAsync *)((char *)this + 24));
  CBlbAsync::LockedIncrement(v4, (unsigned int *)this + 70);
  if ( *((_DWORD *)this + 70) > *((_DWORD *)this + 71) )
    BlbAssert("base\\stor\\blb\\engine\\service\\restore.cpp", 0xA39u, "m_ulBagsProcessed <= m_cBags");
  if ( AppropriateVhdExtension >= 0 )
    goto LABEL_190;
  if ( AppropriateVhdExtension != -2139619048 )
  {
    if ( v3 )
    {
      v51 = BlbPublishVolumeEvent(v3, *(struct _FILETIME *)((char *)this + 356), v50);
      if ( v51 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)v3,
          v51);
      }
    }
  }
  v52 = (void *)*((_QWORD *)this + 43);
  if ( v52 )
  {
    BlbimgFreeContext(v52);
    *((_QWORD *)this + 43) = 0;
  }
  CBlbVolumeRestoreContext::SetAborted(v10, AppropriateVhdExtension, v62);
  v53 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v54 = L"??";
    if ( v3 )
      LODWORD(v54) = (_DWORD)v3;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
      (_DWORD)v54,
      AppropriateVhdExtension);
LABEL_190:
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v63 )
  {
    CoTaskMemFree((LPVOID)v63);
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpFileName )
  {
    CoTaskMemFree((LPVOID)lpFileName);
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    CoTaskMemFree(v3);
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v67[0] )
  {
    CoTaskMemFree(v67[0]);
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v58 )
  {
    FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)v69);
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v53 != &WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 1) != 0 && *((_BYTE *)v53 + 25) >= 4u )
    WPP_SF_(v53[2], 107, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  return (unsigned int)AppropriateVhdExtension;
}

```

## disassembly

```asm
0x14005a62c  push    rbp
0x14005a62e  push    rbx
0x14005a62f  push    rsi
0x14005a630  push    rdi
0x14005a631  push    r12
0x14005a633  push    r13
0x14005a635  push    r14
0x14005a637  push    r15
0x14005a639  lea     rbp, [rsp-0E8h]
0x14005a641  sub     rsp, 1E8h
0x14005a648  mov     rax, cs:__security_cookie
0x14005a64f  xor     rax, rsp
0x14005a652  mov     [rbp+120h+var_50], rax
0x14005a659  mov     rsi, rcx
0x14005a65c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a663  lea     rax, WPP_GLOBAL_Control
0x14005a66a  mov     edi, 1
0x14005a66f  cmp     rcx, rax
0x14005a672  jz      short loc_14005A693
0x14005a674  test    [rcx+1Ch], dil
0x14005a678  jz      short loc_14005A693
0x14005a67a  cmp     byte ptr [rcx+19h], 4
0x14005a67e  jb      short loc_14005A693
0x14005a680  mov     rcx, [rcx+10h]
0x14005a684  lea     edx, [rdi+52h]
0x14005a687  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a68e  call    WPP_SF_
0x14005a693  mov     eax, [rsi+110h]
0x14005a699  xor     r13d, r13d
0x14005a69c  xor     edx, edx; Val
0x14005a69e  mov     [rbp+120h+var_188], r13d
0x14005a6a2  mov     r8d, 0D0h; Size
0x14005a6a8  mov     [rbp+120h+lpszVolumeName], r13
0x14005a6ac  mov     r14d, r13d
0x14005a6af  mov     [rbp+120h+lpFileName], r13
0x14005a6b3  lea     rcx, [rax+rax*2]
0x14005a6b7  mov     [rbp+120h+var_180], r13
0x14005a6bb  shl     rcx, 6
0x14005a6bf  add     rcx, [rsi+108h]
0x14005a6c6  mov     [rbp+120h+var_1A0], rcx
0x14005a6ca  lea     rcx, [rbp+120h+var_130]; void *
0x14005a6ce  mov     dword ptr [rsp+220h+var_1AC], r13d
0x14005a6d3  mov     [rbp+120h+var_170], r13
0x14005a6d7  mov     [rbp+120h+var_168], r13
0x14005a6db  mov     [rbp+120h+pv], r13
0x14005a6df  mov     [rbp+120h+var_150], r13
0x14005a6e3  mov     [rbp+120h+var_158], r13
0x14005a6e7  mov     [rsp+220h+var_1B0], r13b
0x14005a6ec  mov     byte ptr [rsp+220h+var_1AC+4], r13b
0x14005a6f1  mov     [rbp+120h+var_160], r13
0x14005a6f5  mov     [rbp+120h+var_60], r13
0x14005a6fc  mov     [rbp+120h+var_58], r13
0x14005a703  call    memset_0
0x14005a708  lea     r12, [rsi+8]
0x14005a70c  mov     rcx, r12; this
0x14005a70f  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x14005a714  mov     rbx, rax
0x14005a717  test    rax, rax
0x14005a71a  jnz     short loc_14005A734
0x14005a71c  lea     r8, aPcatalogsystem; "pCatalogSystem"
0x14005a723  mov     edx, 8B5h; unsigned int
0x14005a728  lea     rcx, aBaseStorBlbEng_22; "base\\stor\\blb\\engine\\service\\resto"...
0x14005a72f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14005a734  mov     rcx, [rbx]
0x14005a737  lea     r8, [rbp+120h+var_130]
0x14005a73b  movups  xmm0, xmmword ptr [rsi+0D0h]
0x14005a742  mov     r9b, dil
0x14005a745  lea     rdx, [rbp+120h+var_140]
0x14005a749  mov     rax, [rcx+58h]
0x14005a74d  mov     rcx, rbx
0x14005a750  movdqu  xmmword ptr [rbp+120h+var_140], xmm0
0x14005a755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a75a  mov     edi, eax
0x14005a75c  test    eax, eax
0x14005a75e  js      loc_14005AE11
0x14005a764  mov     edx, [rbp+120h+var_6C]; unsigned int
0x14005a76a  lea     r9, [rsp+220h+var_1B0]; unsigned __int8 *
0x14005a76f  mov     ecx, [rbp+120h+var_70]; unsigned int
0x14005a775  lea     r8, [rbp+120h+var_160]; unsigned __int16 **
0x14005a779  mov     byte ptr [rsp+220h+var_1AC+4], 1
0x14005a77e  call    ?BlbGetAppropriateVhdExtension@@YAJKKPEAPEAGPEAE@Z; BlbGetAppropriateVhdExtension(ulong,ulong,ushort * *,uchar *)
0x14005a783  mov     edi, eax
0x14005a785  test    eax, eax
0x14005a787  js      loc_14005AE11
0x14005a78d  mov     r12, [rbp+120h+var_160]
0x14005a791  test    r12, r12
0x14005a794  jnz     short loc_14005A7AE
0x14005a796  lea     r8, aWszvhdextensio; "wszVhdExtension != NULL"
0x14005a79d  mov     edx, 8C7h; unsigned int
0x14005a7a2  lea     rcx, aBaseStorBlbEng_22; "base\\stor\\blb\\engine\\service\\resto"...
0x14005a7a9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14005a7ae  mov     r15, [rbp+120h+var_1A0]
0x14005a7b2  lea     rdx, [rbp+120h+lpszVolumeName]; unsigned __int16 **
0x14005a7b6  mov     rcx, r15; this
0x14005a7b9  call    ?GetRestoreTargetPath@CBlbVolumeRestoreContext@@QEAAJPEAPEAG@Z; CBlbVolumeRestoreContext::GetRestoreTargetPath(ushort * *)
0x14005a7be  mov     edi, eax
0x14005a7c0  test    eax, eax
0x14005a7c2  js      loc_14005B255
0x14005a7c8  mov     r8d, [r15+4Ch]; unsigned int
0x14005a7cc  lea     rcx, [rbp+120h+var_180]
0x14005a7d0  mov     [rsp+220h+var_200], rcx; unsigned __int16 **
0x14005a7d5  lea     rdx, [r15+3Ch]; Uuid
0x14005a7d9  mov     rcx, [rsi+0C8h]; unsigned __int16 *
0x14005a7e0  mov     r9, r12; unsigned __int16 *
0x14005a7e3  call    ?BlbAppendBagFile@@YAJPEAGPEAU_GUID@@KPEBGPEAPEAG@Z; BlbAppendBagFile(ushort *,_GUID *,ulong,ushort const *,ushort * *)
0x14005a7e8  mov     edi, eax
0x14005a7ea  test    eax, eax
0x14005a7ec  js      loc_14005B255
0x14005a7f2  test    byte ptr [r15+4Ch], 8
0x14005a7f7  mov     r14d, 1
0x14005a7fd  movzx   r12d, r13b
0x14005a801  jz      short loc_14005A80C
0x14005a803  test    byte ptr [r15+4Ch], 20h
0x14005a808  cmovz   r12d, r14d
0x14005a80c  lea     r13, [rsi+18h]
0x14005a810  xor     edx, edx; unsigned __int8
0x14005a812  mov     rcx, r13; this
0x14005a815  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x14005a81a  mov     edi, eax
0x14005a81c  test    eax, eax
0x14005a81e  js      loc_14005B255
0x14005a824  mov     rbx, [rbp+120h+var_180]
0x14005a828  xor     r8d, r8d
0x14005a82b  mov     rcx, rbx
0x14005a82e  call    ?BlbVerifyFileNotCompressedOrEncrypted@@YAJPEBGW4_BLB_MEDIA_TYPE@@EE@Z; BlbVerifyFileNotCompressedOrEncrypted(ushort const *,_BLB_MEDIA_TYPE,uchar,uchar)
0x14005a833  mov     edi, eax
0x14005a835  test    eax, eax
0x14005a837  jns     short loc_14005A87D
0x14005a839  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a840  lea     r13, WPP_GLOBAL_Control
0x14005a847  cmp     rcx, r13
0x14005a84a  jz      short loc_14005A874
0x14005a84c  test    [rcx+1Ch], r14b
0x14005a850  jz      short loc_14005A874
0x14005a852  cmp     byte ptr [rcx+19h], 2
0x14005a856  jb      short loc_14005A874
0x14005a858  mov     rcx, [rcx+10h]
0x14005a85c  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a863  mov     edx, 54h ; 'T'
0x14005a868  mov     dword ptr [rsp+220h+var_200], eax
0x14005a86c  mov     r9, rbx
0x14005a86f  call    WPP_SF_Sd
0x14005a874  mov     r14, [rbp+120h+lpszVolumeName]
0x14005a878  jmp     loc_14005B260
0x14005a87d  mov     rcx, r13; this
0x14005a880  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x14005a885  mov     r8b, r14b
0x14005a888  mov     edx, 3
0x14005a88d  mov     rcx, rsi
0x14005a890  call    ?SetState@CBlbRestoreAsync@@IEAAXW4_BLB_RESTORE_STATE@@E@Z; CBlbRestoreAsync::SetState(_BLB_RESTORE_STATE,uchar)
0x14005a895  mov     r14, [rbp+120h+lpszVolumeName]
0x14005a899  lea     rdx, [rbp+120h+lpFileName]; unsigned __int16 **
0x14005a89d  mov     rcx, r14; unsigned __int16 *
0x14005a8a0  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x14005a8a5  mov     edi, eax
0x14005a8a7  test    eax, eax
0x14005a8a9  js      loc_14005B259
0x14005a8af  cmp     qword ptr [rsi+158h], 0
0x14005a8b7  jnz     loc_14005AC16
0x14005a8bd  mov     ebx, [r15+4Ch]
0x14005a8c1  xor     r8d, r8d; __int64
0x14005a8c4  and     ebx, 2
0x14005a8c7  xor     edx, edx; __int64
0x14005a8c9  mov     rcx, rsi; this
0x14005a8cc  call    ?UpdateBytes@CBlbRestoreAsync@@AEAAX_J0@Z; CBlbRestoreAsync::UpdateBytes(__int64,__int64)
0x14005a8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a8d8  lea     rax, WPP_GLOBAL_Control
0x14005a8df  cmp     rcx, rax
0x14005a8e2  jz      short loc_14005A912
0x14005a8e4  test    byte ptr [rcx+1Ch], 1
0x14005a8e8  jz      short loc_14005A912
0x14005a8ea  cmp     byte ptr [rcx+19h], 4
0x14005a8ee  jb      short loc_14005A912
0x14005a8f0  mov     eax, [rsi+110h]
0x14005a8f6  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a8fd  mov     rcx, [rcx+10h]
0x14005a901  mov     edx, 55h ; 'U'
0x14005a906  mov     r9, r14
0x14005a909  mov     dword ptr [rsp+220h+var_200], eax
0x14005a90d  call    WPP_SF_Sd
0x14005a912  test    ebx, ebx
0x14005a914  jnz     short loc_14005A928
0x14005a916  mov     rcx, rsi; this
0x14005a919  call    ?HandleBitLockerBeforeRestore@CBlbRestoreAsync@@AEAAJXZ; CBlbRestoreAsync::HandleBitLockerBeforeRestore(void)
0x14005a91e  mov     edi, eax
0x14005a920  test    eax, eax
0x14005a922  js      loc_14005B259
0x14005a928  lea     r8, [r15+0B0h]
0x14005a92f  mov     r15, [rbp+120h+lpFileName]
0x14005a933  mov     rcx, r15; lpFileName
0x14005a936  lea     rdx, [rsp+220h+var_1AC]
0x14005a93b  call    BlbimgRecordRecoveryTargetBadClusExtents
0x14005a940  mov     ebx, eax
0x14005a942  test    eax, eax
0x14005a944  jz      short loc_14005A9A3
0x14005a946  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a94d  lea     r13, WPP_GLOBAL_Control
0x14005a954  cmp     rcx, r13
0x14005a957  jz      short loc_14005A989
0x14005a959  test    byte ptr [rcx+1Ch], 1
0x14005a95d  jz      short loc_14005A989
0x14005a95f  cmp     byte ptr [rcx+19h], 2
0x14005a963  jb      short loc_14005A989
0x14005a965  mov     edx, 56h ; 'V'
0x14005a96a  mov     r9, r15
0x14005a96d  mov     eax, dword ptr [rsp+220h+var_1AC]
0x14005a971  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a978  mov     rcx, [rcx+10h]
0x14005a97c  mov     dword ptr [rsp+220h+var_1F8], eax
0x14005a980  mov     dword ptr [rsp+220h+var_200], ebx
0x14005a984  call    WPP_SF_SLd
0x14005a989  mov     edx, dword ptr [rsp+220h+var_1AC]
0x14005a98d  lea     r8, [rbp+120h+var_188]
0x14005a991  mov     ecx, ebx
0x14005a993  call    ?BlbTranslateBlbimgError@@YAJW4_BLBIMG_RESULT_CODE@@KPEAJ@Z; BlbTranslateBlbimgError(_BLBIMG_RESULT_CODE,ulong,long *)
0x14005a998  mov     edi, eax
0x14005a99a  mov     r15, [rbp+120h+var_1A0]
0x14005a99e  jmp     loc_14005B260
0x14005a9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9aa  lea     rax, WPP_GLOBAL_Control
0x14005a9b1  cmp     rcx, rax
0x14005a9b4  jz      short loc_14005A9E5
0x14005a9b6  test    byte ptr [rcx+1Ch], 1
0x14005a9ba  jz      short loc_14005A9E5
0x14005a9bc  cmp     byte ptr [rcx+19h], 4
0x14005a9c0  mov     rbx, [rbp+120h+var_180]
0x14005a9c4  jb      short loc_14005A9E9
0x14005a9c6  mov     rcx, [rcx+10h]
0x14005a9ca  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005a9d1  mov     edx, 57h ; 'W'
0x14005a9d6  mov     [rsp+220h+var_200], rbx
0x14005a9db  mov     r9, r15
0x14005a9de  call    WPP_SF_SS
0x14005a9e3  jmp     short loc_14005A9E9
0x14005a9e5  mov     rbx, [rbp+120h+var_180]
0x14005a9e9  call    cs:__imp_GetTickCount
0x14005a9ef  test    byte ptr [rsi+148h], 2
0x14005a9f6  mov     r15d, eax
0x14005a9f9  jnz     loc_14005AB5E
0x14005a9ff  cmp     [rsp+220h+var_1B0], 0
0x14005aa04  jnz     loc_14005AB5E
0x14005aa0a  lea     rax, [rbp+120h+pv]
0x14005aa0e  xor     r9d, r9d; unsigned __int16 *
0x14005aa11  mov     [rsp+220h+var_1F8], rax; unsigned __int16 **
0x14005aa16  xor     r8d, r8d; unsigned int
0x14005aa19  mov     rdx, rbx; PCWSTR
0x14005aa1c  mov     dword ptr [rsp+220h+var_200], 0; unsigned int
0x14005aa24  mov     rcx, r13; this
0x14005aa27  call    ?MountVolume@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGK1KPEAPEAG@Z; CBlbVhdHelper::MountVolume(CBlbImpersonationHelper *,ushort const *,ulong,ushort const *,ulong,ushort * *)
0x14005aa2c  mov     edi, eax
0x14005aa2e  test    eax, eax
0x14005aa30  jns     short loc_14005AA7F
0x14005aa32  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa39  lea     r13, WPP_GLOBAL_Control
0x14005aa40  cmp     rcx, r13
0x14005aa43  jz      loc_14005A99A
0x14005aa49  test    byte ptr [rcx+1Ch], 1
0x14005aa4d  jz      loc_14005A99A
0x14005aa53  cmp     byte ptr [rcx+19h], 2
0x14005aa57  jb      loc_14005A99A
0x14005aa5d  mov     r9, [rbp+120h+pv]
0x14005aa61  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005aa68  mov     rcx, [rcx+10h]
0x14005aa6c  mov     edx, 58h ; 'X'
0x14005aa71  mov     dword ptr [rsp+220h+var_200], eax
0x14005aa75  call    WPP_SF_Sd
0x14005aa7a  jmp     loc_14005A99A
0x14005aa7f  mov     r10, [rbp+120h+pv]
0x14005aa83  test    r10, r10
0x14005aa86  jnz     short loc_14005AAA4
0x14005aa88  lea     r8, aWszmountedvhdp; "wszMountedVhdPath != NULL"
0x14005aa8f  mov     edx, 93Fh; unsigned int
0x14005aa94  lea     rcx, aBaseStorBlbEng_22; "base\\stor\\blb\\engine\\service\\resto"...
0x14005aa9b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14005aaa0  mov     r10, [rbp+120h+pv]
0x14005aaa4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aaab  lea     rax, WPP_GLOBAL_Control
0x14005aab2  cmp     rcx, rax
0x14005aab5  jz      short loc_14005AAE4
0x14005aab7  test    byte ptr [rcx+1Ch], 1
0x14005aabb  jz      short loc_14005AAE4
0x14005aabd  cmp     byte ptr [rcx+19h], 4
0x14005aac1  jb      short loc_14005AAE4
0x14005aac3  mov     rcx, [rcx+10h]
0x14005aac7  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005aace  mov     edx, 59h ; 'Y'
0x14005aad3  mov     [rsp+220h+var_200], r10
0x14005aad8  mov     r9, rbx
0x14005aadb  call    WPP_SF_SS
0x14005aae0  mov     r10, [rbp+120h+pv]
0x14005aae4  mov     rcx, [rbp+120h+var_1A0]
0x14005aae8  mov     ebx, 1
0x14005aaed  mov     r8b, [rsi+161h]
0x14005aaf4  mov     r9b, bl
0x14005aaf7  mov     dl, [rsi+160h]
0x14005aafd  mov     eax, [rcx+4Ch]
0x14005ab00  lea     rcx, [rsp+220h+var_1AC]
0x14005ab05  mov     [rsp+220h+var_1B8], rcx
0x14005ab0a  lea     rcx, [rbp+120h+var_158]
0x14005ab0e  mov     [rsp+220h+var_1C0], rcx
  ... truncated ...
```
