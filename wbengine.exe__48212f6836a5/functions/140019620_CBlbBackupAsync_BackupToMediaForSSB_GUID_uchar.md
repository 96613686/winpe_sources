# CBlbBackupAsync::BackupToMediaForSSB(_GUID *,uchar *)

- ea: `0x140019620`
- end: `0x140019fc3`
- name: `?BackupToMediaForSSB@CBlbBackupAsync@@AEAAJPEAU_GUID@@PEAE@Z`
- size: `2467`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct _GUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002e188`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x140013008`
- `0x140015ad8`
- `0x140019620`
- `0x14002db88`
- `0x14002e4e0`
- `0x140030ea8`
- `0x1400377d0`
- `0x140037ddc`
- `0x140039ec0`
- `0x14003c434`
- `0x140078f88`
- `0x140079410`
- `0x14007aaac`
- `0x14007ab2c`
- `0x1400820f8`
- `0x140082700`
- `0x1400889f0`
- `0x1400f38e4`
- `0x14011b8a0`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140019bac`
- `ole32!CoTaskMemAlloc` at `0x140019bac`
- `ole32!CoTaskMemFree` at `0x140019e98`
- `ole32!CoTaskMemFree` at `0x140019ebf`
- `ole32!CoTaskMemFree` at `0x140019ed8`
- `ole32!CoTaskMemFree` at `0x140019ef1`
- `ole32!CoTaskMemFree` at `0x140019f0a`
- `ole32!CoTaskMemFree` at `0x140019f33`
- `ole32!CoTaskMemFree` at `0x140019f4c`
- `ole32!CoTaskMemFree` at `0x140019e98`
- `ole32!CoTaskMemFree` at `0x140019ebf`
- `ole32!CoTaskMemFree` at `0x140019ed8`
- `ole32!CoTaskMemFree` at `0x140019ef1`
- `ole32!CoTaskMemFree` at `0x140019f0a`
- `ole32!CoTaskMemFree` at `0x140019f33`
- `ole32!CoTaskMemFree` at `0x140019f4c`
- `RPCRT4!UuidCreate` at `0x140019c43`
- `RPCRT4!UuidCreate` at `0x140019c43`

## string_xrefs

- `0x1400196c0`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400196e1`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019702`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019723`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019740`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001975d`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400197c4`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400198f9`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019944`: `base\stor\blb\engine\service\backup.cpp`
- `0x140019961`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::BackupToMediaForSSB(CBlbBackupAsync *this, struct _GUID *a2, unsigned __int8 *a3)
{
  CBlbSystemStateBackupAsync *v6; // rcx
  void *v7; // rsi
  struct _BLBSRV_VOLUME_USN_INFO *v8; // r12
  unsigned int v9; // r15d
  int SSBVolumes; // eax
  struct _BLBSRV_VOLUME_MAP *v11; // r13
  int v12; // edi
  unsigned int v13; // r14d
  unsigned int i; // r15d
  __int64 v15; // r9
  __int64 v16; // rsi
  struct _BLBSRV_VOLUME_USN_INFO *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // r14d
  unsigned int j; // esi
  unsigned int v22; // eax
  __int64 v23; // r8
  char v24; // cl
  CBlbVolumeBackupContext *v25; // r8
  int v26; // eax
  unsigned int v27; // edi
  __int64 v28; // r8
  __int64 v29; // r8
  _OWORD *v30; // rax
  unsigned int v31; // r14d
  unsigned int v32; // r15d
  GUID v33; // xmm0
  __int64 v34; // rcx
  __int64 v35; // rsi
  __int64 v36; // rax
  PVOID *v37; // rcx
  unsigned int k; // edi
  __int64 v39; // r8
  char v40; // cl
  CBlbVolumeBackupContext *v41; // r8
  PVOID *v42; // rcx
  __int64 m; // rsi
  void *v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  unsigned int n; // ebx
  __int64 v48; // rsi
  void *v49; // rcx
  int v51; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v52; // [rsp+54h] [rbp-15h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h]
  struct _BLBSRV_VOLUME_MAP *v54; // [rsp+60h] [rbp-9h] BYREF
  struct _BLBSRV_VOLUME_USN_INFO *v55; // [rsp+68h] [rbp-1h] BYREF
  struct _GUID *v56; // [rsp+70h] [rbp+7h]
  UUID Uuid; // [rsp+78h] [rbp+Fh] BYREF

  *(_QWORD *)&Uuid.Data1 = a3;
  v56 = a2;
  v6 = (CBlbSystemStateBackupAsync *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 494, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v7 = 0;
  pv = 0;
  v8 = 0;
  v54 = 0;
  v9 = 0;
  v52 = 0;
  v55 = 0;
  if ( !*((_BYTE *)this + 390) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CBDu, "m_bSystemState");
  if ( !*((_QWORD *)this + 103) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CBEu, "m_pSSBContext");
  if ( !*((_QWORD *)this + 105) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CBFu, "m_rgVolumeMap");
  if ( !*((_DWORD *)this + 212) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CC0u, "m_cVolumeMap");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CC1u, "pguidMediaId");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CC2u, "pbTargetFailure");
  *a3 = 0;
  SSBVolumes = CBlbSystemStateBackupAsync::GetSSBVolumes(
                 v6,
                 *((struct CBlbVolumeBackupContext **)this + 27),
                 *((_DWORD *)this + 92),
                 *((OLECHAR **)this + 105),
                 *((_DWORD *)this + 212),
                 &v54,
                 &v52);
  v11 = v54;
  v12 = SSBVolumes;
  v51 = SSBVolumes;
  if ( SSBVolumes < 0 )
    goto LABEL_84;
  if ( !v52 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2CCFu, "cVolumeSSB");
  v51 = CBlbSystemStateBackupAsync::SetVolumeMap(*((CBlbSystemStateBackupAsync **)this + 103), v11, v52);
  v12 = v51;
  if ( v51 < 0 )
    goto LABEL_84;
  v9 = v52;
  LODWORD(v54) = v52;
  v51 = BlbutilMemalloc((void **)&v55, v52, 0x38u);
  v12 = v51;
  if ( v51 < 0 )
  {
    v8 = v55;
    goto LABEL_84;
  }
  v13 = 0;
  for ( i = 0; i < *((_DWORD *)this + 92); ++i )
  {
    v15 = *((_QWORD *)this + 27);
    v16 = 368LL * i;
    if ( (*(_BYTE *)(v16 + v15 + 84) & 0x20) != 0 && *(_DWORD *)(v16 + v15 + 20) != 12 )
    {
      v17 = v55;
      v18 = 56LL * v13;
      *(_QWORD *)((char *)v55 + v18 + 16) = *(_QWORD *)(v16 + v15 + 272);
      *(_QWORD *)((char *)v17 + v18 + 24) = *(_QWORD *)(v16 + v15 + 280);
      *(_QWORD *)((char *)v17 + v18 + 32) = *(_QWORD *)(v16 + v15 + 288);
      *(_QWORD *)((char *)v17 + v18 + 40) = *(_QWORD *)(v16 + v15 + 296);
      *(_QWORD *)((char *)v17 + v18 + 48) = *(_QWORD *)(v16 + v15 + 304);
      *((_BYTE *)v17 + v18) = *(_BYTE *)(v16 + v15 + 256);
      v51 = BlbutilDuplicateString(
              *(const unsigned __int16 **)(v16 + v15 + 264),
              (unsigned __int16 **)((char *)v17 + v18 + 8),
              0);
      v12 = v51;
      if ( v51 < 0 )
        goto LABEL_140;
      v19 = *((_QWORD *)this + 27);
      ++v13;
      if ( (*(_BYTE *)(v16 + v19 + 84) & 4) == 0 && *(_DWORD *)(v16 + v19 + 20) != 12 )
      {
        if ( *(int *)(v16 + v19 + 32) < 0 )
          BlbAssert(
            "base\\stor\\blb\\engine\\service\\backup.cpp",
            0x2D0Du,
            "SUCCEEDED(m_rgVolumeContext[iVol].m_hrResult)");
        v51 = CBlbBackupAsync::SkipVolumeFromSystemStateBackup(
                this,
                (struct CBlbVolumeBackupContext *)(v16 + *((_QWORD *)this + 27)));
        v12 = v51;
        if ( v51 < 0 )
        {
LABEL_140:
          v8 = v55;
          goto LABEL_82;
        }
        LODWORD(v8) = (_DWORD)v8 + 1;
      }
    }
  }
  v9 = (unsigned int)v54;
  if ( v13 != (_DWORD)v54 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2D18u, "iVolumeUsnInfo == cVolumeUsnInfo");
  if ( (unsigned int)v8 >= v13 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x2D19u, "cSkippedVolumes < iVolumeUsnInfo");
  v51 = CBlbFileAsync::InitializeFileLogging(
          *((CBlbFileAsync **)this + 103),
          *(struct _FILETIME *)((char *)this + 392),
          L"Backup",
          L"Backup_Error");
  v12 = v51;
  if ( v51 < 0 )
  {
    v8 = v55;
LABEL_62:
    v7 = pv;
    goto LABEL_84;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 495, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  CBlbSystemStateBackupAsync::SetState(*((_QWORD *)this + 103), 2);
  v8 = v55;
  v51 = CBlbSystemStateBackupAsync::EnumerateFiles(*((CBlbSystemStateBackupAsync **)this + 103), v9, v55);
  v12 = v51;
  if ( v51 < 0 )
    goto LABEL_54;
  v51 = CBlbBackupAsync::PrepareTargetVolumesForSSB(this, v11, v52);
  v12 = v51;
  if ( v51 < 0 )
    goto LABEL_54;
  v51 = CBlbSystemStateBackupAsync::SetVolumeMap(*((CBlbSystemStateBackupAsync **)this + 103), v11, v52);
  v12 = v51;
  if ( v51 < 0 )
    goto LABEL_54;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 496, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  CBlbSystemStateBackupAsync::SetState(*((_QWORD *)this + 103), 3);
  v51 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 103) + 128LL))(*((_QWORD *)this + 103));
  v12 = v51;
  if ( v51 < 0 )
  {
    if ( *((_DWORD *)this + 84) == 4 && (unsigned int)BlbIsNetworkError(*((_DWORD *)this + 9), 0) )
      CBlbAsync::SetResult((CBlbBackupAsync *)((char *)this + 24), -2139618981, *((_DWORD *)this + 9), 0);
LABEL_54:
    v7 = pv;
    goto LABEL_84;
  }
  v20 = *((_DWORD *)this + 58);
  for ( j = 0; ; ++j )
  {
    v22 = *((_DWORD *)this + 92);
    if ( j >= v22 )
      break;
    v23 = *((_QWORD *)this + 27) + 368LL * j;
    if ( BlbIsVolumeIncludedForSSB(*(_DWORD *)(v23 + 84), *(_BYTE *)(v23 + 104)) )
    {
      if ( (v24 & 8) == 0 )
      {
        v26 = CBlbVolumeBackupContext::PerformVHDCompaction(v25);
        v51 = v26;
        v12 = v26;
        if ( v26 < 0 )
        {
          CBlbAsync::SetResult((CBlbBackupAsync *)((char *)this + 24), -2139618991, v26, 0);
          goto LABEL_62;
        }
      }
    }
  }
  v27 = 0;
  *((_DWORD *)this + 58) = v20;
  if ( v22 )
  {
    do
    {
      v28 = *((_QWORD *)this + 27) + 368LL * v27;
      if ( BlbIsVolumeIncludedForSSB(*(_DWORD *)(v28 + 84), *(_BYTE *)(v28 + 104)) )
      {
        if ( *(int *)(v29 + 32) < 0 )
          CBlbVolumeBackupContext::SetVolumeVolumeFlags(v29, 4);
        else
          *(_DWORD *)(v29 + 20) = 14;
      }
      ++v27;
    }
    while ( v27 < *((_DWORD *)this + 92) );
  }
  v51 = CBlbBackupAsync::WriteBackupMetadata(this, *(unsigned __int8 **)&Uuid.Data1);
  v12 = v51;
  if ( v51 < 0 )
    goto LABEL_62;
  v30 = CoTaskMemAlloc(0x10u);
  pv = v30;
  v7 = v30;
  if ( v30 )
  {
    v31 = 0;
    v32 = 0;
    *v30 = 0;
    if ( *((_DWORD *)this + 92) )
    {
      v33 = GUID_NULL;
      do
      {
        v34 = *((_QWORD *)this + 27);
        v35 = 368LL * v31;
        Uuid = v33;
        if ( *(_BYTE *)(v35 + v34 + 104) )
        {
          v36 = v35 + v34;
          if ( (*(int *)(v35 + v34 + 32) < 0 || (*(_BYTE *)(v36 + 84) & 8) == 0 && (*(_BYTE *)(v36 + 84) & 0x40) == 0)
            && (*(_DWORD *)(v36 + 84) & 0x1000) == 0 )
          {
            UuidCreate(&Uuid);
            *(_QWORD *)(v35 + *((_QWORD *)this + 27) + 120) = *((_QWORD *)this + 49);
            *(_DWORD *)(v35 + *((_QWORD *)this + 27) + 128) = 0;
            v51 = CBlbBackupAsync::AddBagToLocalCatalog(
                    this,
                    &Uuid,
                    v32,
                    (struct _GUID *)(v35 + *((_QWORD *)this + 27) + 68LL),
                    *(_DWORD *)(v35 + *((_QWORD *)this + 27) + 84),
                    v56,
                    (unsigned __int8 *)pv,
                    (struct _FILETIME *)(v35 + *((_QWORD *)this + 27) + 120LL),
                    *(_DWORD *)(v35 + *((_QWORD *)this + 27) + 128));
            v12 = v51;
            if ( v51 < 0 )
              break;
            v33 = GUID_NULL;
            ++v32;
          }
        }
        ++v31;
      }
      while ( v31 < *((_DWORD *)this + 92) );
LABEL_82:
      v7 = pv;
    }
    v9 = (unsigned int)v54;
LABEL_84:
    if ( v12 >= 0 )
      goto LABEL_110;
    goto LABEL_85;
  }
  v12 = -2147024882;
  v51 = -2147024882;
LABEL_85:
  v37 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 497, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v37 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 == -2139618978 )
  {
    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 && *((_BYTE *)v37 + 25) >= 4u )
      WPP_SF_(v37[2], 498, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    for ( k = 0; k < *((_DWORD *)this + 92); ++k )
    {
      v39 = *((_QWORD *)this + 27) + 368LL * k;
      if ( BlbIsVolumeIncludedForSSB(*(_DWORD *)(v39 + 84), *(_BYTE *)(v39 + 104))
        && (v40 & 8) == 0
        && *((_BYTE *)v41 + 346) != 1
        && (int)CBlbVolumeBackupContext::PerformVHDCompaction(v41) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 499, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
    }
    if ( (int)CBlbBackupAsync::OverrideErrorIfSourceDedup(this, &v51, 2) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 500, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    v12 = v51;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 103) + 64LL))(
      *((_QWORD *)this + 103),
      (unsigned int)v51,
      *((unsigned int *)this + 9));
  }
LABEL_110:
  if ( (int)CBlbFileAsync::StopFileLogging(*((CBlbFileAsync **)this + 103)) >= 0 )
  {
LABEL_115:
    v42 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_116;
  }
  v42 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 501, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    goto LABEL_115;
  }
LABEL_116:
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v42 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    for ( m = 0; (unsigned int)m < v52; m = (unsigned int)(m + 1) )
    {
      v44 = (void *)*((_QWORD *)v11 + 3 * m);
      if ( v44 )
      {
        CoTaskMemFree(v44);
        *((_QWORD *)v11 + 3 * m) = 0;
      }
      v45 = (void *)*((_QWORD *)v11 + 3 * m + 1);
      if ( v45 )
      {
        CoTaskMemFree(v45);
        *((_QWORD *)v11 + 3 * m + 1) = 0;
      }
      v46 = (void *)*((_QWORD *)v11 + 3 * m + 2);
      if ( v46 )
      {
        CoTaskMemFree(v46);
        *((_QWORD *)v11 + 3 * m + 2) = 0;
      }
    }
    CoTaskMemFree(v11);
    v42 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    for ( n = 0; n < v9; ++n )
    {
      v48 = 56LL * n;
      v49 = *(void **)((char *)v8 + v48 + 8);
      if ( v49 )
      {
        CoTaskMemFree(v49);
        *(_QWORD *)((char *)v8 + v48 + 8) = 0;
      }
    }
    CoTaskMemFree(v8);
    v42 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v42 != &WPP_GLOBAL_Control && (*((_BYTE *)v42 + 28) & 1) != 0 && *((_BYTE *)v42 + 25) >= 4u )
    WPP_SF_(v42[2], 502, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140019620  mov     [rsp-8+arg_18], rbx
0x140019625  push    rbp
0x140019626  push    rsi
0x140019627  push    rdi
0x140019628  push    r12
0x14001962a  push    r13
0x14001962c  push    r14
0x14001962e  push    r15
0x140019630  lea     rbp, [rsp-27h]
0x140019635  sub     rsp, 90h
0x14001963c  mov     rax, cs:__security_cookie
0x140019643  xor     rax, rsp
0x140019646  mov     [rbp+57h+var_38], rax
0x14001964a  mov     rdi, r8
0x14001964d  mov     qword ptr [rbp+57h+Uuid.Data1], r8
0x140019651  mov     r14, rdx
0x140019654  mov     [rbp+57h+var_50], rdx
0x140019658  mov     rbx, rcx
0x14001965b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019662  lea     rax, WPP_GLOBAL_Control
0x140019669  cmp     rcx, rax
0x14001966c  jz      short loc_14001968F
0x14001966e  test    byte ptr [rcx+1Ch], 1
0x140019672  jz      short loc_14001968F
0x140019674  cmp     byte ptr [rcx+19h], 4
0x140019678  jb      short loc_14001968F
0x14001967a  mov     rcx, [rcx+10h]
0x14001967e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140019685  mov     edx, 1EEh
0x14001968a  call    WPP_SF_
0x14001968f  xor     r13d, r13d
0x140019692  mov     esi, r13d
0x140019695  mov     [rbp+57h+pv], r13
0x140019699  mov     r12d, r13d
0x14001969c  mov     [rbp+57h+var_60], r13
0x1400196a0  mov     r15d, r13d
0x1400196a3  mov     [rbp+57h+var_6C], r13d
0x1400196a7  mov     [rbp+57h+var_58], r13
0x1400196ab  cmp     [rbx+186h], r13b
0x1400196b2  jnz     short loc_1400196CC
0x1400196b4  lea     r8, aMBsystemstate; "m_bSystemState"
0x1400196bb  mov     edx, 2CBDh; unsigned int
0x1400196c0  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400196c7  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400196cc  cmp     [rbx+338h], r13
0x1400196d3  jnz     short loc_1400196ED
0x1400196d5  lea     r8, aMPssbcontext; "m_pSSBContext"
0x1400196dc  mov     edx, 2CBEh; unsigned int
0x1400196e1  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400196e8  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400196ed  cmp     [rbx+348h], r13
0x1400196f4  jnz     short loc_14001970E
0x1400196f6  lea     r8, aMRgvolumemap; "m_rgVolumeMap"
0x1400196fd  mov     edx, 2CBFh; unsigned int
0x140019702  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140019709  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001970e  cmp     [rbx+350h], r13d
0x140019715  jnz     short loc_14001972F
0x140019717  lea     r8, aMCvolumemap; "m_cVolumeMap"
0x14001971e  mov     edx, 2CC0h; unsigned int
0x140019723  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14001972a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001972f  test    r14, r14
0x140019732  jnz     short loc_14001974C
0x140019734  lea     r8, aPguidmediaid; "pguidMediaId"
0x14001973b  mov     edx, 2CC1h; unsigned int
0x140019740  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140019747  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001974c  test    rdi, rdi
0x14001974f  jnz     short loc_140019769
0x140019751  lea     r8, aPbtargetfailur; "pbTargetFailure"
0x140019758  mov     edx, 2CC2h; unsigned int
0x14001975d  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140019764  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140019769  mov     [rdi], sil
0x14001976c  lea     rax, [rbp+57h+var_6C]
0x140019770  mov     r9, [rbx+348h]; struct _BLBSRV_VOLUME_MAP *
0x140019777  mov     r8d, [rbx+170h]; unsigned int
0x14001977e  mov     rdx, [rbx+0D8h]; struct CBlbVolumeBackupContext *
0x140019785  mov     [rsp+0C0h+var_90], rax; unsigned int *
0x14001978a  lea     rax, [rbp+57h+var_60]
0x14001978e  mov     [rsp+0C0h+var_98], rax; struct _BLBSRV_VOLUME_MAP **
0x140019793  mov     eax, [rbx+350h]
0x140019799  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x14001979d  call    ?GetSSBVolumes@CBlbSystemStateBackupAsync@@QEAAJPEAVCBlbVolumeBackupContext@@KPEAU_BLBSRV_VOLUME_MAP@@KPEAPEAU3@PEAK@Z; CBlbSystemStateBackupAsync::GetSSBVolumes(CBlbVolumeBackupContext *,ulong,_BLBSRV_VOLUME_MAP *,ulong,_BLBSRV_VOLUME_MAP * *,ulong *)
0x1400197a2  mov     r13, [rbp+57h+var_60]
0x1400197a6  mov     edi, eax
0x1400197a8  mov     [rbp+57h+var_70], eax
0x1400197ab  test    eax, eax
0x1400197ad  js      loc_140019CE7
0x1400197b3  cmp     [rbp+57h+var_6C], esi
0x1400197b6  jnz     short loc_1400197D0
0x1400197b8  lea     r8, aCvolumessb; "cVolumeSSB"
0x1400197bf  mov     edx, 2CCFh; unsigned int
0x1400197c4  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400197cb  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400197d0  mov     r8d, [rbp+57h+var_6C]; unsigned int
0x1400197d4  mov     rdx, r13; struct _BLBSRV_VOLUME_MAP *
0x1400197d7  mov     rcx, [rbx+338h]; this
0x1400197de  call    ?SetVolumeMap@CBlbSystemStateBackupAsync@@QEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z; CBlbSystemStateBackupAsync::SetVolumeMap(_BLBSRV_VOLUME_MAP *,ulong)
0x1400197e3  mov     [rbp+57h+var_70], eax
0x1400197e6  mov     edi, eax
0x1400197e8  test    eax, eax
0x1400197ea  js      loc_140019CE7
0x1400197f0  mov     r15d, [rbp+57h+var_6C]
0x1400197f4  lea     rcx, [rbp+57h+var_58]; void **
0x1400197f8  mov     edx, r15d; unsigned int
0x1400197fb  mov     dword ptr [rbp+57h+var_60], r15d
0x1400197ff  mov     r8d, 38h ; '8'; unsigned int
0x140019805  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14001980a  mov     [rbp+57h+var_70], eax
0x14001980d  mov     edi, eax
0x14001980f  test    eax, eax
0x140019811  js      loc_140019FA8
0x140019817  xor     r14d, r14d
0x14001981a  xor     r15d, r15d
0x14001981d  cmp     r15d, [rbx+170h]
0x140019824  jnb     loc_14001992F
0x14001982a  mov     r9, [rbx+0D8h]
0x140019831  mov     eax, r15d
0x140019834  imul    rsi, rax, 170h
0x14001983b  test    byte ptr [rsi+r9+54h], 20h
0x140019841  jz      loc_140019927
0x140019847  cmp     dword ptr [rsi+r9+14h], 0Ch
0x14001984d  jz      loc_140019927
0x140019853  mov     rdx, [rbp+57h+var_58]
0x140019857  xor     r8d, r8d; unsigned __int64
0x14001985a  mov     eax, r14d
0x14001985d  imul    rcx, rax, 38h ; '8'
0x140019861  mov     rax, [rsi+r9+110h]
0x140019869  mov     [rcx+rdx+10h], rax
0x14001986e  mov     rax, [rsi+r9+118h]
0x140019876  mov     [rcx+rdx+18h], rax
0x14001987b  mov     rax, [rsi+r9+120h]
0x140019883  mov     [rcx+rdx+20h], rax
0x140019888  mov     rax, [rsi+r9+128h]
0x140019890  mov     [rcx+rdx+28h], rax
0x140019895  mov     rax, [rsi+r9+130h]
0x14001989d  mov     [rcx+rdx+30h], rax
0x1400198a2  mov     al, [rsi+r9+100h]
0x1400198aa  mov     [rcx+rdx], al
0x1400198ad  add     rdx, 8
0x1400198b1  add     rdx, rcx; unsigned __int16 **
0x1400198b4  mov     rcx, [rsi+r9+108h]; unsigned __int16 *
0x1400198bc  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400198c1  mov     [rbp+57h+var_70], eax
0x1400198c4  mov     edi, eax
0x1400198c6  test    eax, eax
0x1400198c8  js      loc_140019FB1
0x1400198ce  mov     rax, [rbx+0D8h]
0x1400198d5  inc     r14d
0x1400198d8  test    byte ptr [rsi+rax+54h], 4
0x1400198dd  jnz     short loc_140019927
0x1400198df  cmp     dword ptr [rsi+rax+14h], 0Ch
0x1400198e4  jz      short loc_140019927
0x1400198e6  cmp     dword ptr [rsi+rax+20h], 0
0x1400198eb  jge     short loc_140019905
0x1400198ed  lea     r8, aSucceededMRgvo; "SUCCEEDED(m_rgVolumeContext[iVol].m_hrR"...
0x1400198f4  mov     edx, 2D0Dh; unsigned int
0x1400198f9  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140019900  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140019905  mov     rdx, [rbx+0D8h]
0x14001990c  mov     rcx, rbx; this
0x14001990f  add     rdx, rsi; struct CBlbVolumeBackupContext *
0x140019912  call    ?SkipVolumeFromSystemStateBackup@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@@Z; CBlbBackupAsync::SkipVolumeFromSystemStateBackup(CBlbVolumeBackupContext *)
0x140019917  mov     [rbp+57h+var_70], eax
0x14001991a  mov     edi, eax
0x14001991c  test    eax, eax
0x14001991e  js      loc_140019FB1
0x140019924  inc     r12d
0x140019927  inc     r15d
0x14001992a  jmp     loc_14001981D
0x14001992f  mov     r15d, dword ptr [rbp+57h+var_60]
0x140019933  cmp     r14d, r15d
0x140019936  jz      short loc_140019950
0x140019938  lea     r8, aIvolumeusninfo; "iVolumeUsnInfo == cVolumeUsnInfo"
0x14001993f  mov     edx, 2D18h; unsigned int
0x140019944  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14001994b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140019950  cmp     r12d, r14d
0x140019953  jb      short loc_14001996D
0x140019955  lea     r8, aCskippedvolume; "cSkippedVolumes < iVolumeUsnInfo"
0x14001995c  mov     edx, 2D19h; unsigned int
0x140019961  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140019968  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001996d  mov     rdx, [rbx+188h]; struct _FILETIME
0x140019974  lea     r9, aBackupError; "Backup_Error"
0x14001997b  mov     rcx, [rbx+338h]; this
0x140019982  lea     r8, aBackup_1; "Backup"
0x140019989  call    ?InitializeFileLogging@CBlbFileAsync@@QEAAJU_FILETIME@@PEAG1@Z; CBlbFileAsync::InitializeFileLogging(_FILETIME,ushort *,ushort *)
0x14001998e  mov     [rbp+57h+var_70], eax
0x140019991  mov     edi, eax
0x140019993  test    eax, eax
0x140019995  js      loc_140019FBA
0x14001999b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199a2  lea     r14, WPP_GLOBAL_Control
0x1400199a9  cmp     rcx, r14
0x1400199ac  jz      short loc_1400199CF
0x1400199ae  test    byte ptr [rcx+1Ch], 1
0x1400199b2  jz      short loc_1400199CF
0x1400199b4  cmp     byte ptr [rcx+19h], 4
0x1400199b8  jb      short loc_1400199CF
0x1400199ba  mov     rcx, [rcx+10h]
0x1400199be  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400199c5  mov     edx, 1EFh
0x1400199ca  call    WPP_SF_
0x1400199cf  mov     rcx, [rbx+338h]
0x1400199d6  mov     edx, 2
0x1400199db  call    ?SetState@CBlbSystemStateBackupAsync@@QEAAXW4_BLB_SYSTEM_STATE_BACKUP_STATE@@E@Z; CBlbSystemStateBackupAsync::SetState(_BLB_SYSTEM_STATE_BACKUP_STATE,uchar)
0x1400199e0  mov     r12, [rbp+57h+var_58]
0x1400199e4  mov     edx, r15d; unsigned int
0x1400199e7  mov     rcx, [rbx+338h]; this
0x1400199ee  mov     r8, r12; struct _BLBSRV_VOLUME_USN_INFO *
0x1400199f1  call    ?EnumerateFiles@CBlbSystemStateBackupAsync@@QEAAJKPEAU_BLBSRV_VOLUME_USN_INFO@@@Z; CBlbSystemStateBackupAsync::EnumerateFiles(ulong,_BLBSRV_VOLUME_USN_INFO *)
0x1400199f6  mov     [rbp+57h+var_70], eax
0x1400199f9  mov     edi, eax
0x1400199fb  test    eax, eax
0x1400199fd  js      loc_140019AC8
0x140019a03  mov     r8d, [rbp+57h+var_6C]; unsigned int
0x140019a07  mov     rdx, r13; struct _BLBSRV_VOLUME_MAP *
0x140019a0a  mov     rcx, rbx; this
0x140019a0d  call    ?PrepareTargetVolumesForSSB@CBlbBackupAsync@@AEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z; CBlbBackupAsync::PrepareTargetVolumesForSSB(_BLBSRV_VOLUME_MAP *,ulong)
0x140019a12  mov     [rbp+57h+var_70], eax
0x140019a15  mov     edi, eax
0x140019a17  test    eax, eax
0x140019a19  js      loc_140019AC8
0x140019a1f  mov     r8d, [rbp+57h+var_6C]; unsigned int
0x140019a23  mov     rdx, r13; struct _BLBSRV_VOLUME_MAP *
0x140019a26  mov     rcx, [rbx+338h]; this
0x140019a2d  call    ?SetVolumeMap@CBlbSystemStateBackupAsync@@QEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z; CBlbSystemStateBackupAsync::SetVolumeMap(_BLBSRV_VOLUME_MAP *,ulong)
0x140019a32  mov     [rbp+57h+var_70], eax
0x140019a35  mov     edi, eax
0x140019a37  test    eax, eax
0x140019a39  js      loc_140019AC8
0x140019a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a46  cmp     rcx, r14
0x140019a49  jz      short loc_140019A6C
0x140019a4b  test    byte ptr [rcx+1Ch], 1
0x140019a4f  jz      short loc_140019A6C
0x140019a51  cmp     byte ptr [rcx+19h], 4
0x140019a55  jb      short loc_140019A6C
0x140019a57  mov     rcx, [rcx+10h]
0x140019a5b  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140019a62  mov     edx, 1F0h
0x140019a67  call    WPP_SF_
0x140019a6c  mov     rcx, [rbx+338h]
0x140019a73  mov     edx, 3
0x140019a78  call    ?SetState@CBlbSystemStateBackupAsync@@QEAAXW4_BLB_SYSTEM_STATE_BACKUP_STATE@@E@Z; CBlbSystemStateBackupAsync::SetState(_BLB_SYSTEM_STATE_BACKUP_STATE,uchar)
0x140019a7d  mov     rcx, [rbx+338h]
0x140019a84  mov     rax, [rcx]
0x140019a87  mov     rax, [rax+80h]
0x140019a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019a93  mov     [rbp+57h+var_70], eax
0x140019a96  mov     edi, eax
0x140019a98  test    eax, eax
0x140019a9a  jns     short loc_140019AD1
0x140019a9c  cmp     dword ptr [rbx+150h], 4
0x140019aa3  jnz     short loc_140019AC8
0x140019aa5  mov     ecx, [rbx+24h]; int
0x140019aa8  xor     edx, edx; int
0x140019aaa  call    ?BlbIsNetworkError@@YAHJH@Z; BlbIsNetworkError(long,int)
0x140019aaf  test    eax, eax
0x140019ab1  jz      short loc_140019AC8
0x140019ab3  mov     r8d, [rbx+24h]; int
0x140019ab7  lea     rcx, [rbx+18h]; this
0x140019abb  xor     r9d, r9d; unsigned __int8
0x140019abe  mov     edx, 8078015Bh; int
0x140019ac3  call    ?SetResult@CBlbAsync@@QEAAXJJE@Z; CBlbAsync::SetResult(long,long,uchar)
0x140019ac8  mov     rsi, [rbp+57h+pv]
0x140019acc  jmp     loc_140019CEE
0x140019ad1  mov     r14d, [rbx+0E8h]
0x140019ad8  xor     esi, esi
0x140019ada  mov     eax, [rbx+170h]
0x140019ae0  cmp     esi, eax
0x140019ae2  jnb     short loc_140019B3C
0x140019ae4  mov     eax, esi
0x140019ae6  imul    r8, rax, 170h
0x140019aed  add     r8, [rbx+0D8h]
0x140019af4  mov     dl, [r8+68h]; unsigned __int8
0x140019af8  mov     ecx, [r8+54h]; unsigned int
0x140019afc  call    ?BlbIsVolumeIncludedForSSB@@YAEKE@Z; BlbIsVolumeIncludedForSSB(ulong,uchar)
0x140019b01  test    al, al
0x140019b03  jz      short loc_140019B1B
0x140019b05  test    cl, 8
0x140019b08  jnz     short loc_140019B1B
0x140019b0a  mov     rcx, r8; this
0x140019b0d  call    ?PerformVHDCompaction@CBlbVolumeBackupContext@@QEAAJXZ; CBlbVolumeBackupContext::PerformVHDCompaction(void)
0x140019b12  mov     [rbp+57h+var_70], eax
0x140019b15  mov     edi, eax
0x140019b17  test    eax, eax
0x140019b19  js      short loc_140019B1F
0x140019b1b  inc     esi
0x140019b1d  jmp     short loc_140019ADA
0x140019b1f  lea     rcx, [rbx+18h]; this
0x140019b23  xor     r9d, r9d; unsigned __int8
0x140019b26  mov     r8d, eax; int
0x140019b29  mov     edx, 80780151h; int
0x140019b2e  call    ?SetResult@CBlbAsync@@QEAAXJJE@Z; CBlbAsync::SetResult(long,long,uchar)
0x140019b33  mov     rsi, [rbp+57h+pv]
0x140019b37  jmp     loc_140019CE7
  ... truncated ...
```
