# CBlbBackupAsync::SetIncrementalBackupStatus(void)

- ea: `0x140035dd0`
- end: `0x140036c87`
- name: `?SetIncrementalBackupStatus@CBlbBackupAsync@@AEAAJXZ`
- size: `3767`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014200`
- `0x140014260`
- `0x140014384`
- `0x140014448`
- `0x14001dad0`
- `0x14001e0b8`
- `0x14001e664`
- `0x14002667c`
- `0x140026dfc`
- `0x1400278a4`
- `0x140035dd0`
- `0x1400377d0`
- `0x1400889f0`
- `0x140088d0c`
- `0x1400923f0`
- `0x140098c04`
- `0x14009e734`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f81d0`
- `0x140108b34`
- `0x14012e834`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140035f2e`
- `ole32!CoTaskMemFree` at `0x14003678c`
- `ole32!CoTaskMemFree` at `0x140036adb`
- `ole32!CoTaskMemFree` at `0x140036b20`
- `ole32!CoTaskMemFree` at `0x140036b2e`
- `ole32!CoTaskMemFree` at `0x140035f2e`
- `ole32!CoTaskMemFree` at `0x14003678c`
- `ole32!CoTaskMemFree` at `0x140036adb`
- `ole32!CoTaskMemFree` at `0x140036b20`
- `ole32!CoTaskMemFree` at `0x140036b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x140036076`
- `OLEAUT32!__imp_SysFreeString` at `0x1400360f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400361e8`
- `OLEAUT32!__imp_SysFreeString` at `0x14003629d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003634d`
- `OLEAUT32!__imp_SysFreeString` at `0x140036408`
- `OLEAUT32!__imp_SysFreeString` at `0x140036487`
- `OLEAUT32!__imp_SysFreeString` at `0x140036552`
- `OLEAUT32!__imp_SysFreeString` at `0x140036622`
- `OLEAUT32!__imp_SysFreeString` at `0x140036636`
- `OLEAUT32!__imp_SysFreeString` at `0x14003664a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036743`
- `OLEAUT32!__imp_SysFreeString` at `0x140036c67`
- `OLEAUT32!__imp_SysFreeString` at `0x140036076`
- `OLEAUT32!__imp_SysFreeString` at `0x1400360f8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400361e8`
- `OLEAUT32!__imp_SysFreeString` at `0x14003629d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003634d`
- `OLEAUT32!__imp_SysFreeString` at `0x140036408`
- `OLEAUT32!__imp_SysFreeString` at `0x140036487`
- `OLEAUT32!__imp_SysFreeString` at `0x140036552`
- `OLEAUT32!__imp_SysFreeString` at `0x140036622`
- `OLEAUT32!__imp_SysFreeString` at `0x140036636`
- `OLEAUT32!__imp_SysFreeString` at `0x14003664a`
- `OLEAUT32!__imp_SysFreeString` at `0x140036743`
- `OLEAUT32!__imp_SysFreeString` at `0x140036c67`

## string_xrefs

- `0x1400368ee`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::SetIncrementalBackupStatus(CBlbBackupAsync *this)
{
  int v1; // esi
  unsigned __int16 *v3; // rbx
  void *v4; // rdi
  struct _BLBCAT_COMPONENT_INFO *v5; // r14
  unsigned int v6; // edx
  __int64 v7; // rax
  int ComponentsList; // r15d
  CBlbBackupAsync *v9; // rdi
  struct _BLBCAT_BACKUP_SET_INFO *v10; // r13
  unsigned int v11; // r12d
  unsigned int v12; // eax
  __int64 v13; // r14
  int OriginalAccessPath; // eax
  int v15; // ebx
  ATL::CComBSTR *v16; // rax
  ATL::CComBSTR *v17; // rax
  ATL::CComBSTR *v18; // rax
  unsigned int j; // edx
  struct _GUID *v20; // r12
  __int64 v21; // r13
  __int64 v22; // rcx
  __int64 v23; // rax
  ATL::CComBSTR *v24; // rax
  _QWORD *v25; // rbx
  bool v26; // zf
  ATL::CComBSTR *v27; // rax
  struct _GUID v28; // xmm0
  unsigned int v29; // r8d
  ATL::CComBSTR *v30; // rax
  ATL::CComBSTR *v31; // rax
  unsigned __int16 *v32; // r9
  unsigned int v33; // r8d
  ATL::CComBSTR *v34; // rax
  __int64 v35; // rdi
  __int64 v36; // rbx
  _QWORD *v37; // rdi
  _QWORD *v38; // r12
  __int64 v39; // rcx
  ATL::CComBSTR *v40; // rax
  CBlbBackupAsync *v41; // rbx
  struct _GUID *v42; // rbx
  unsigned int k; // edx
  _QWORD *v44; // r8
  __int64 v45; // rax
  unsigned __int64 v46; // rcx
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  CBlbBackupAsync *v49; // rsi
  unsigned int m; // edx
  __int64 v51; // r8
  __int64 v52; // rax
  struct _BLBCAT_BACKUP_SET_INFO *v53; // rsi
  unsigned int v55; // r14d
  __int64 v56; // rcx
  __int64 v57; // rax
  const wchar_t *v58; // rbx
  int v59; // edi
  ATL::CComBSTR *v60; // rax
  unsigned __int8 v61; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v62[7]; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int16 *v63; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct _BLBCAT_COMPONENT_INFO *v65; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v66; // [rsp+60h] [rbp-A0h] BYREF
  char v67; // [rsp+61h] [rbp-9Fh]
  int LastBackupInfoForIncremental; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 v69; // [rsp+68h] [rbp-98h]
  struct _BLBCAT_BACKUP_SET_INFO *v70; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v73; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v74; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v75; // [rsp+88h] [rbp-78h]
  CBlbBackupAsync *v76; // [rsp+90h] [rbp-70h]
  struct _BLB_VOLUME_INFO *v77; // [rsp+98h] [rbp-68h] BYREF
  struct _BLB_VOLUME_INFO *i; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v79; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v80; // [rsp+B0h] [rbp-50h]
  BSTR v81; // [rsp+B8h] [rbp-48h] BYREF
  BSTR v82; // [rsp+C0h] [rbp-40h] BYREF
  BSTR v83; // [rsp+C8h] [rbp-38h] BYREF
  BSTR v84; // [rsp+D0h] [rbp-30h] BYREF
  BSTR v85; // [rsp+D8h] [rbp-28h] BYREF
  BSTR v86; // [rsp+E0h] [rbp-20h] BYREF
  BSTR v87; // [rsp+E8h] [rbp-18h] BYREF
  BSTR v88; // [rsp+F0h] [rbp-10h] BYREF
  BSTR v89; // [rsp+F8h] [rbp-8h] BYREF
  BSTR v90; // [rsp+100h] [rbp+0h] BYREF
  __int64 v91; // [rsp+108h] [rbp+8h]
  BSTR bstrString[2]; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v93; // [rsp+120h] [rbp+20h] BYREF
  __int128 v94; // [rsp+130h] [rbp+30h] BYREF
  __int128 v95; // [rsp+140h] [rbp+40h]
  __int128 v96; // [rsp+150h] [rbp+50h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  struct _GUID Buf1; // [rsp+168h] [rbp+68h] BYREF
  struct _GUID v99; // [rsp+178h] [rbp+78h] BYREF

  v76 = this;
  v1 = 0;
  v75 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 765, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v3 = 0;
  v70 = 0;
  v4 = 0;
  v61 = 0;
  v5 = 0;
  v63 = 0;
  v6 = 0;
  pv = 0;
  v62[0] = 0;
  v73 = 0;
  v77 = 0;
  v72 = 0;
  v65 = 0;
  v74 = 0;
  for ( i = 0; v6 < *((_DWORD *)this + 92); *(_BYTE *)(368 * v7 + *((_QWORD *)this + 27) + 132) = 1 )
    v7 = v6++;
  v69 = BlbutilCheckTestHook(L"ForceFullBackup");
  LastBackupInfoForIncremental = CBlbBackupAsync::GetLastBackupInfoForIncremental(this, &v70);
  ComponentsList = LastBackupInfoForIncremental;
  if ( LastBackupInfoForIncremental >= 0 )
  {
    v9 = v76;
    v10 = v70;
    v11 = 0;
    v67 = 0;
    while ( 1 )
    {
      v12 = *((_DWORD *)v9 + 92);
      v71 = v11;
      if ( v11 >= v12 )
        break;
      v61 = 0;
      v62[0] = 0;
      v13 = *((_QWORD *)v9 + 27) + 368LL * v11;
      *(_BYTE *)(v13 + 256) = 0;
      *(_DWORD *)(v13 + 364) = 0;
      if ( v3 )
      {
        CoTaskMemFree(v3);
        v63 = 0;
      }
      OriginalAccessPath = CBlbVolumeBackupContext::GetOriginalAccessPath((CBlbVolumeBackupContext *)v13, &v63);
      v3 = v63;
      ComponentsList = OriginalAccessPath;
      if ( OriginalAccessPath < 0 )
        goto LABEL_179;
      LastBackupInfoForIncremental = BlbutilSlashTerminatePath(v63, (LPVOID *)(v13 + 264));
      ComponentsList = LastBackupInfoForIncremental;
      if ( LastBackupInfoForIncremental < 0 )
        goto LABEL_179;
      if ( v69 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 766, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        *(_DWORD *)(v13 + 364) = 1;
      }
      else if ( v10 )
      {
        v15 = *(_DWORD *)(v13 + 360);
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v16 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, (const struct _GUID *)(v13 + 68));
            v1 |= 1u;
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              768,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              *(_QWORD *)v16,
              v15);
          }
          if ( (v1 & 1) != 0 )
          {
            v1 &= ~1u;
            SysFreeString(bstrString[0]);
          }
          *(_DWORD *)(v13 + 364) = 3;
        }
        else if ( (*(_BYTE *)(v13 + 84) & 8) != 0 || !*(_BYTE *)(v13 + 344) )
        {
          LastBackupInfoForIncremental = CBlbBackupAsync::CheckIfAutomaticFullBackupRequired(
                                           v9,
                                           (struct CBlbVolumeBackupContext *)v13,
                                           &v61);
          ComponentsList = LastBackupInfoForIncremental;
          if ( LastBackupInfoForIncremental < 0 )
          {
            v47 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v48 = 770;
LABEL_164:
              WPP_SF_d(v47[2], v48, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            goto LABEL_165;
          }
          if ( v61 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 771, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            *(_DWORD *)(v13 + 364) = 5;
          }
          else
          {
            if ( !*(_QWORD *)(v13 + 224) || (*(_BYTE *)(v13 + 84) & 0x10) != 0 )
            {
              for ( j = 0; ; ++j )
              {
                v75 = j;
                if ( j >= *((_DWORD *)v10 + 16) )
                  goto LABEL_126;
                v20 = (struct _GUID *)(v13 + 68);
                v21 = 120LL * j;
                v22 = *((_QWORD *)v70 + 9);
                v91 = v22;
                v23 = *(_QWORD *)(v22 + v21) - *(_QWORD *)(v13 + 68);
                if ( !v23 )
                  v23 = *(_QWORD *)(v22 + v21 + 8) - *(_QWORD *)(v13 + 76);
                if ( !v23 )
                  break;
                v10 = v70;
              }
              if ( *(char *)(v22 + v21 + 16) < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  v24 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v83, (const struct _GUID *)(v13 + 68));
                  v1 |= 8u;
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    773,
                    &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                    *(_QWORD *)v24);
                }
                if ( (v1 & 8) != 0 )
                {
                  v1 &= ~8u;
                  SysFreeString(v83);
                }
                *(_DWORD *)(v13 + 364) = 6;
                goto LABEL_72;
              }
              v25 = (_QWORD *)(v21 + v22 + 96);
              v26 = (*(_BYTE *)(v13 + 84) & 0x10) == 0;
              v80 = v25;
              if ( v26 )
              {
                Buf1 = *(struct _GUID *)(v22 + v21 + 80);
                if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    v27 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v84, (const struct _GUID *)(v13 + 68));
                    v1 |= 0x10u;
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      774,
                      &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                      *(_QWORD *)v27);
                  }
                  if ( (v1 & 0x10) != 0 )
                  {
                    v1 &= ~0x10u;
                    SysFreeString(v84);
                  }
                  *(_DWORD *)(v13 + 364) = 7;
                  goto LABEL_72;
                }
                if ( (*(_BYTE *)(v13 + 84) & 8) == 0 )
                {
                  v28 = *v20;
                  v29 = *(_DWORD *)(v13 + 84);
                  v66 = 0;
                  v93 = v28;
                  LastBackupInfoForIncremental = CBlbBackupAsync::CheckIfIncrementalBackupPossible(
                                                   (CBlbBackupAsync *)&v66,
                                                   &v93,
                                                   v29,
                                                   (struct _BLB_VOLUME_USN_INFO *)v25,
                                                   (struct _BLB_VOLUME_USN_INFO *)(v13 + 232),
                                                   &v66);
                  ComponentsList = LastBackupInfoForIncremental;
                  if ( LastBackupInfoForIncremental < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    {
                      v30 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v85, (const struct _GUID *)(v13 + 68));
                      v1 |= 0x20u;
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        775,
                        &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                        *(_QWORD *)v30);
                    }
                    if ( (v1 & 0x20) != 0 )
                    {
                      v1 &= ~0x20u;
                      SysFreeString(v85);
                    }
                    ComponentsList = 0;
                    *(_DWORD *)(v13 + 364) = 9;
                    LastBackupInfoForIncremental = 0;
                    goto LABEL_72;
                  }
                  if ( !v66 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    {
                      v31 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v86, (const struct _GUID *)(v13 + 68));
                      v1 |= 0x40u;
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        776,
                        &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                        *(_QWORD *)v31);
                    }
                    if ( (v1 & 0x40) != 0 )
                    {
                      v1 &= ~0x40u;
                      SysFreeString(v86);
                    }
                    *(_DWORD *)(v13 + 364) = 8;
                    goto LABEL_72;
                  }
                }
                v99 = GUID_NULL;
                ComponentsList = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)v9 + 40), 0);
                if ( ComponentsList < 0 )
                  goto LABEL_178;
                v32 = (unsigned __int16 *)*((_QWORD *)v9 + 59);
                v33 = *(_DWORD *)(v13 + 84);
                v93 = *v20;
                LastBackupInfoForIncremental = CBlbVhdHelper::GetVhdSnapshotId(
                                                 (CBlbBackupAsync *)((char *)v9 + 40),
                                                 &v93,
                                                 v33,
                                                 v32,
                                                 &v99);
                ComponentsList = LastBackupInfoForIncremental;
                if ( LastBackupInfoForIncremental < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    v34 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v87, (const struct _GUID *)(v13 + 68));
                    v1 |= 0x80u;
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      777,
                      &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                      *(_QWORD *)v34);
                  }
                  if ( (v1 & 0x80u) != 0 )
                  {
                    v1 &= ~0x80u;
                    SysFreeString(v87);
                  }
                  ComponentsList = 0;
                  *(_DWORD *)(v13 + 364) = 11;
                  LastBackupInfoForIncremental = 0;
                  goto LABEL_72;
                }
                CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v9 + 40));
                if ( memcmp_0(&v99, &Buf1, 0x10u) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    v35 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v90, &Buf1);
                    v36 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v89, &v99);
                    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v88, (const struct _GUID *)(v13 + 68));
                    v1 |= 0x700u;
                    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v35);
                  }
                  if ( (v1 & 0x400) != 0 )
                  {
                    v1 &= ~0x400u;
                    SysFreeString(v88);
                  }
                  if ( (v1 & 0x200) != 0 )
                  {
                    v1 &= ~0x200u;
                    SysFreeString(v89);
                  }
                  if ( (v1 & 0x100) != 0 )
                  {
                    v1 &= ~0x100u;
                    SysFreeString(v90);
                  }
                  *(_DWORD *)(v13 + 364) = 10;
                  goto LABEL_72;
                }
                v25 = v80;
              }
              if ( (*(_BYTE *)(v13 + 84) & 8) != 0 )
              {
                v37 = (_QWORD *)(v13 + 240);
                v38 = (_QWORD *)(v13 + 248);
                goto LABEL_123;
              }
              v97 = 0;
              v94 = 0;
              v95 = 0;
              v96 = 0;
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              ComponentsList = BlbutilDuplicateString(
                                 *(const unsigned __int16 **)(v13 + 264),
                                 (unsigned __int16 **)&pv,
                                 0);
              if ( ComponentsList >= 0 )
              {
                v37 = (_QWORD *)(v13 + 240);
                v38 = (_QWORD *)(v13 + 248);
                *((_QWORD *)&v94 + 1) = pv;
                v95 = *(_OWORD *)v25;
                *(_QWORD *)&v96 = v25[2];
                *((_QWORD *)&v96 + 1) = *(_QWORD *)(v13 + 240);
                v97 = *(_QWORD *)(v13 + 248);
                LOBYTE(v94) = 1;
                if ( v67 )
                {
LABEL_145:
                  v42 = 0;
                  for ( k = 0; k < v73; ++k )
                  {
                    v44 = (_QWORD *)((char *)v77 + 128 * (unsigned __int64)k);
                    v45 = *(_QWORD *)(v13 + 68);
                    v46 = *v44 - v45;
                    if ( *v44 == v45 )
                      v46 = v44[1] - _mm_srli_si128(*(__m128i *)(v13 + 68), 8).m128i_u64[0];
                    if ( !v46 )
                    {
                      v42 = (struct _GUID *)((char *)v77 + 128 * (unsigned __int64)k);
                      if ( v44 )
                        goto LABEL_153;
                      break;
                    }
                  }
                  BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x4893u, "pCurVolumeInfo");
LABEL_153:
                  LastBackupInfoForIncremental = CBlbBackupAsync::CheckIfHardlinkChangeDetected(
                                                   v76,
                                                   v42,
                                                   v70,
                                                   (struct CBlbVolumeBackupContext *)v13,
                                                   (struct _BLBSRV_VOLUME_USN_INFO *)&v94,
                                                   v62);
                  ComponentsList = LastBackupInfoForIncremental;
                  if ( LastBackupInfoForIncremental >= 0 )
                  {
                    if ( v62[0] )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          783,
                          &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
                      }
                      *(_DWORD *)(v13 + 364) = 13;
LABEL_72:
                      v10 = v70;
                    }
                    else
                    {
LABEL_123:
                      if ( (*(_BYTE *)(v13 + 84) & 8) == 0 )
                      {
                        v39 = v91;
                        *(_QWORD *)(v13 + 272) = *v80;
                        *(_QWORD *)(v13 + 280) = *(_QWORD *)(v39 + v21 + 104);
                        *(_QWORD *)(v13 + 288) = *(_QWORD *)(v39 + v21 + 112);
                        *(_QWORD *)(v13 + 296) = *v37;
                        *(_QWORD *)(v13 + 304) = *v38;
                        *(_BYTE *)(v13 + 256) = 1;
                      }
                      CBlbVolumeBackupContext::SetVolumeVolumeFlags(v13, 16);
                      v10 = v70;
                    }
LABEL_126:
                    if ( v75 == *((_DWORD *)v10 + 16) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        v40 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v79, (const struct _GUID *)(v13 + 68));
                        v1 |= 0x800u;
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          784,
                          &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                          *(_QWORD *)v40);
                      }
                      if ( (v1 & 0x800) != 0 )
                      {
                        v1 &= ~0x800u;
                        SysFreeString(v79);
                      }
                      *(_DWORD *)(v13 + 364) = 12;
                    }
                    v11 = v71;
                    v9 = v76;
                    goto LABEL_135;
                  }
                  v47 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v48 = 782;
                    goto LABEL_164;
                  }
                }
                else
                {
                  v41 = v76;
                  ComponentsList = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, struct _BLB_VOLUME_INFO **))(**((_QWORD **)v76 + 10) + 64LL))(
                                     *((_QWORD *)v76 + 10),
                                     &v74,
                                     &i);
                  if ( ComponentsList < 0 )
                  {
                    v47 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v48 = 779;
                      goto LABEL_164;
                    }
                  }
                  else
                  {
                    ComponentsList = CBlbBackupAsync::GetComponentsList(v41, &v65, &v72);
                    if ( ComponentsList < 0 )
                    {
                      v47 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v48 = 780;
                        goto LABEL_164;
                      }
                    }
                    else
                    {
                      ComponentsList = CBlbBackupItemsHelper::GetAllFileSpecs(
                                         v74,
                                         i,
                                         *((unsigned __int16 **)v41 + 107),
                                         v72,
                                         v65,
                                         *((struct _SPP_METADATA_PROP **)v41 + 57),
                                         &v73,
                                         &v77);
                      if ( ComponentsList >= 0 )
                      {
                        v67 = 1;
                        goto LABEL_145;
                      }
                      v47 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v48 = 781;
                        goto LABEL_164;
                      }
                    }
                  }
                }
LABEL_165:
                v3 = v63;
                goto LABEL_179;
              }
              goto LABEL_178;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v18 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v82, (const struct _GUID *)(v13 + 68));
              v1 |= 4u;
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                772,
                &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                *(_QWORD *)v18);
            }
            if ( (v1 & 4) != 0 )
            {
              v1 &= ~4u;
              SysFreeString(v82);
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v17 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v81, (const struct _GUID *)(v13 + 68));
            v1 |= 2u;
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              769,
              &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              *(_QWORD *)v17);
          }
          if ( (v1 & 2) != 0 )
          {
            v1 &= ~2u;
            SysFreeString(v81);
          }
          *(_DWORD *)(v13 + 364) = 4;
        }
LABEL_135:
        v3 = v63;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 767, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        *(_DWORD *)(v13 + 364) = 2;
      }
      ++v11;
    }
    v55 = 0;
    if ( v12 )
    {
      do
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v56 = 368LL * v55;
          v57 = *((_QWORD *)v9 + 27);
          v58 = L"is";
          v59 = *(_DWORD *)(v56 + v57 + 364);
          if ( (*(_BYTE *)(v56 + v57 + 84) & 0x10) == 0 )
            v58 = L"is NOT";
          v60 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v79, (const struct _GUID *)(v56 + v57 + 68));
          v1 |= 0x1000u;
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            785,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            *(_QWORD *)v60,
            (__int64)v58,
            v59);
          v9 = v76;
        }
        if ( (v1 & 0x1000) != 0 )
        {
          v1 &= ~0x1000u;
          SysFreeString(v79);
        }
        ++v55;
      }
      while ( v55 < *((_DWORD *)v9 + 92) );
      ComponentsList = LastBackupInfoForIncremental;
LABEL_178:
      v3 = v63;
    }
LABEL_179:
    v5 = v65;
    v4 = pv;
  }
  v49 = v76;
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)v76 + 40));
  if ( ComponentsList < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 786, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    for ( m = 0; m < *((_DWORD *)v49 + 92); ++m )
    {
      v51 = 368LL * m;
      v52 = *((_QWORD *)v49 + 27);
      if ( (*(_BYTE *)(v51 + v52 + 84) & 8) == 0 )
        *(_BYTE *)(v51 + v52 + 132) = 0;
    }
  }
  v53 = v70;
  if ( v70 )
  {
    FreeBackupSetContents(v70);
    CoTaskMemFree(v53);
  }
  if ( v5 )
    FreeComponentInfo(v72, v5);
  if ( v77 )
    FreeVolumes(&v77, &v73);
  if ( i )
    FreeVolumes(&i, &v74);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 787, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)ComponentsList;
}

```

## disassembly

```asm
0x140035dd0  push    rbp
0x140035dd2  push    rbx
0x140035dd3  push    rsi
0x140035dd4  push    rdi
0x140035dd5  push    r12
0x140035dd7  push    r13
0x140035dd9  push    r14
0x140035ddb  push    r15
0x140035ddd  lea     rbp, [rsp-98h]
0x140035de5  sub     rsp, 198h
0x140035dec  mov     rax, cs:__security_cookie
0x140035df3  xor     rax, rsp
0x140035df6  mov     [rbp+0D0h+var_48], rax
0x140035dfd  xor     eax, eax
0x140035dff  mov     [rbp+0D0h+var_140], rcx
0x140035e03  mov     esi, eax
0x140035e05  mov     [rbp+0D0h+var_148], eax
0x140035e08  mov     r15, rcx
0x140035e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e12  lea     r12, WPP_GLOBAL_Control
0x140035e19  cmp     rcx, r12
0x140035e1c  jz      short loc_140035E41
0x140035e1e  test    byte ptr [rcx+1Ch], 1
0x140035e22  jz      short loc_140035E41
0x140035e24  cmp     byte ptr [rcx+19h], 4
0x140035e28  jb      short loc_140035E41
0x140035e2a  mov     rcx, [rcx+10h]
0x140035e2e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140035e35  mov     edx, 2FDh
0x140035e3a  call    WPP_SF_
0x140035e3f  xor     eax, eax
0x140035e41  mov     rbx, rax
0x140035e44  mov     [rsp+1D0h+var_160], rax
0x140035e49  mov     rdi, rax
0x140035e4c  mov     [rsp+1D0h+var_190], al
0x140035e50  mov     r14, rax
0x140035e53  mov     [rsp+1D0h+var_188], rax
0x140035e58  mov     edx, eax
0x140035e5a  mov     [rsp+1D0h+pv], rax
0x140035e5f  mov     [rsp+1D0h+var_18F], al
0x140035e63  mov     [rbp+0D0h+var_150], eax
0x140035e66  mov     [rbp+0D0h+var_138], rax
0x140035e6a  mov     [rsp+1D0h+var_154], eax
0x140035e6e  mov     [rsp+1D0h+var_178], rax
0x140035e73  mov     [rbp+0D0h+var_14C], eax
0x140035e76  mov     [rbp+0D0h+var_130], rax
0x140035e7a  cmp     [r15+170h], eax
0x140035e81  jbe     short loc_140035EA6
0x140035e83  mov     eax, edx
0x140035e85  inc     edx
0x140035e87  imul    rcx, rax, 170h
0x140035e8e  mov     rax, [r15+0D8h]
0x140035e95  mov     byte ptr [rcx+rax+84h], 1
0x140035e9d  cmp     edx, [r15+170h]
0x140035ea4  jb      short loc_140035E83
0x140035ea6  lea     rcx, aForcefullbacku; "ForceFullBackup"
0x140035ead  call    ?BlbutilCheckTestHook@@YAEPEAG@Z; BlbutilCheckTestHook(ushort *)
0x140035eb2  lea     rdx, [rsp+1D0h+var_160]; struct _BLBCAT_BACKUP_SET_INFO **
0x140035eb7  mov     [rsp+1D0h+var_168], al
0x140035ebb  mov     rcx, r15; this
0x140035ebe  call    ?GetLastBackupInfoForIncremental@CBlbBackupAsync@@QEAAJPEAPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbBackupAsync::GetLastBackupInfoForIncremental(_BLBCAT_BACKUP_SET_INFO * *)
0x140035ec3  mov     [rsp+1D0h+var_16C], eax
0x140035ec7  mov     r15d, eax
0x140035eca  test    eax, eax
0x140035ecc  js      loc_140036A4B
0x140035ed2  mov     rdi, [rbp+0D0h+var_140]
0x140035ed6  xor     cl, cl
0x140035ed8  mov     r13, [rsp+1D0h+var_160]
0x140035edd  xor     r12d, r12d
0x140035ee0  mov     [rsp+1D0h+var_16F], cl
0x140035ee4  mov     eax, [rdi+170h]
0x140035eea  mov     [rsp+1D0h+var_158], r12d
0x140035eef  cmp     r12d, eax
0x140035ef2  jnb     loc_140036BBC
0x140035ef8  mov     [rsp+1D0h+var_190], 0
0x140035efd  mov     [rsp+1D0h+var_18F], 0
0x140035f02  mov     eax, r12d
0x140035f05  imul    r14, rax, 170h
0x140035f0c  add     r14, [rdi+0D8h]
0x140035f13  mov     byte ptr [r14+100h], 0
0x140035f1b  mov     dword ptr [r14+16Ch], 0
0x140035f26  test    rbx, rbx
0x140035f29  jz      short loc_140035F3D
0x140035f2b  mov     rcx, rbx; pv
0x140035f2e  call    cs:__imp_CoTaskMemFree
0x140035f34  mov     [rsp+1D0h+var_188], 0
0x140035f3d  lea     rdx, [rsp+1D0h+var_188]; unsigned __int16 **
0x140035f42  mov     rcx, r14; this
0x140035f45  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x140035f4a  mov     rbx, [rsp+1D0h+var_188]
0x140035f4f  mov     r15d, eax
0x140035f52  test    eax, eax
0x140035f54  js      loc_140036A3A
0x140035f5a  lea     rdx, [r14+108h]; unsigned __int16 **
0x140035f61  mov     rcx, rbx; unsigned __int16 *
0x140035f64  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x140035f69  mov     [rsp+1D0h+var_16C], eax
0x140035f6d  mov     r15d, eax
0x140035f70  test    eax, eax
0x140035f72  js      loc_140036A3A
0x140035f78  cmp     [rsp+1D0h+var_168], 0
0x140035f7d  jz      short loc_140035FC3
0x140035f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f86  lea     rax, WPP_GLOBAL_Control
0x140035f8d  cmp     rcx, rax
0x140035f90  jz      short loc_140035FB3
0x140035f92  test    byte ptr [rcx+1Ch], 1
0x140035f96  jz      short loc_140035FB3
0x140035f98  cmp     byte ptr [rcx+19h], 4
0x140035f9c  jb      short loc_140035FB3
0x140035f9e  mov     rcx, [rcx+10h]
0x140035fa2  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140035fa9  mov     edx, 2FEh
0x140035fae  call    WPP_SF_
0x140035fb3  mov     dword ptr [r14+16Ch], 1
0x140035fbe  jmp     loc_140036762
0x140035fc3  test    r13, r13
0x140035fc6  jnz     short loc_14003600C
0x140035fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140035fcf  lea     rax, WPP_GLOBAL_Control
0x140035fd6  cmp     rcx, rax
0x140035fd9  jz      short loc_140035FFC
0x140035fdb  test    byte ptr [rcx+1Ch], 1
0x140035fdf  jz      short loc_140035FFC
0x140035fe1  cmp     byte ptr [rcx+19h], 4
0x140035fe5  jb      short loc_140035FFC
0x140035fe7  mov     rcx, [rcx+10h]
0x140035feb  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140035ff2  mov     edx, 2FFh
0x140035ff7  call    WPP_SF_
0x140035ffc  mov     dword ptr [r14+16Ch], 2
0x140036007  jmp     loc_140036762
0x14003600c  mov     ebx, [r14+168h]
0x140036013  test    ebx, ebx
0x140036015  jz      short loc_14003608C
0x140036017  mov     rax, cs:WPP_GLOBAL_Control
0x14003601e  lea     rcx, WPP_GLOBAL_Control
0x140036025  cmp     rax, rcx
0x140036028  jz      short loc_140036069
0x14003602a  test    byte ptr [rax+1Ch], 1
0x14003602e  jz      short loc_140036069
0x140036030  cmp     byte ptr [rax+19h], 4
0x140036034  jb      short loc_140036069
0x140036036  lea     rdx, [r14+44h]; struct _GUID *
0x14003603a  lea     rcx, [rbp+0D0h+bstrString]; this
0x14003603e  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x140036043  mov     rcx, cs:WPP_GLOBAL_Control
0x14003604a  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140036051  or      esi, 1
0x140036054  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x140036058  mov     edx, 300h
0x14003605d  mov     r9, [rax]
0x140036060  mov     rcx, [rcx+10h]
0x140036064  call    WPP_SF_Sd
0x140036069  test    sil, 1
0x14003606d  jz      short loc_14003607C
0x14003606f  mov     rcx, [rbp+0D0h+bstrString]; bstrString
0x140036073  and     esi, 0FFFFFFFEh
0x140036076  call    cs:__imp_SysFreeString
0x14003607c  mov     dword ptr [r14+16Ch], 3
0x140036087  jmp     loc_14003675D
0x14003608c  test    byte ptr [r14+54h], 8
0x140036091  jnz     short loc_14003610E
0x140036093  cmp     byte ptr [r14+158h], 0
0x14003609b  jz      short loc_14003610E
0x14003609d  mov     rax, cs:WPP_GLOBAL_Control
0x1400360a4  lea     rcx, WPP_GLOBAL_Control
0x1400360ab  cmp     rax, rcx
0x1400360ae  jz      short loc_1400360EB
0x1400360b0  test    byte ptr [rax+1Ch], 1
0x1400360b4  jz      short loc_1400360EB
0x1400360b6  cmp     byte ptr [rax+19h], 4
0x1400360ba  jb      short loc_1400360EB
0x1400360bc  lea     rdx, [r14+44h]; struct _GUID *
0x1400360c0  lea     rcx, [rbp+0D0h+var_118]; this
0x1400360c4  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x1400360c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400360d0  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400360d7  or      esi, 2
0x1400360da  mov     edx, 301h
0x1400360df  mov     r9, [rax]
0x1400360e2  mov     rcx, [rcx+10h]
0x1400360e6  call    WPP_SF_S
0x1400360eb  test    sil, 2
0x1400360ef  jz      short loc_1400360FE
0x1400360f1  mov     rcx, [rbp+0D0h+var_118]; bstrString
0x1400360f5  and     esi, 0FFFFFFFDh
0x1400360f8  call    cs:__imp_SysFreeString
0x1400360fe  mov     dword ptr [r14+16Ch], 4
0x140036109  jmp     loc_14003675D
0x14003610e  lea     r8, [rsp+1D0h+var_190]; unsigned __int8 *
0x140036113  mov     rdx, r14; struct CBlbVolumeBackupContext *
0x140036116  mov     rcx, rdi; this
0x140036119  call    ?CheckIfAutomaticFullBackupRequired@CBlbBackupAsync@@AEAAJPEAVCBlbVolumeBackupContext@@PEAE@Z; CBlbBackupAsync::CheckIfAutomaticFullBackupRequired(CBlbVolumeBackupContext *,uchar *)
0x14003611e  mov     [rsp+1D0h+var_16C], eax
0x140036122  mov     r15d, eax
0x140036125  test    eax, eax
0x140036127  js      loc_140036B87
0x14003612d  cmp     [rsp+1D0h+var_190], 0
0x140036132  jz      short loc_140036178
0x140036134  mov     rcx, cs:WPP_GLOBAL_Control
0x14003613b  lea     rax, WPP_GLOBAL_Control
0x140036142  cmp     rcx, rax
0x140036145  jz      short loc_140036168
0x140036147  test    byte ptr [rcx+1Ch], 1
0x14003614b  jz      short loc_140036168
0x14003614d  cmp     byte ptr [rcx+19h], 4
0x140036151  jb      short loc_140036168
0x140036153  mov     rcx, [rcx+10h]
0x140036157  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003615e  mov     edx, 303h
0x140036163  call    WPP_SF_
0x140036168  mov     dword ptr [r14+16Ch], 5
0x140036173  jmp     loc_14003675D
0x140036178  cmp     qword ptr [r14+0E0h], 0
0x140036180  jz      short loc_1400361F3
0x140036182  test    byte ptr [r14+54h], 10h
0x140036187  jnz     short loc_1400361F3
0x140036189  mov     rax, cs:WPP_GLOBAL_Control
0x140036190  lea     rcx, WPP_GLOBAL_Control
0x140036197  cmp     rax, rcx
0x14003619a  jz      short loc_1400361D7
0x14003619c  test    byte ptr [rax+1Ch], 1
0x1400361a0  jz      short loc_1400361D7
0x1400361a2  cmp     byte ptr [rax+19h], 4
0x1400361a6  jb      short loc_1400361D7
0x1400361a8  lea     rdx, [r14+44h]; struct _GUID *
0x1400361ac  lea     rcx, [rbp+0D0h+var_110]; this
0x1400361b0  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x1400361b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400361bc  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400361c3  or      esi, 4
0x1400361c6  mov     edx, 304h
0x1400361cb  mov     r9, [rax]
0x1400361ce  mov     rcx, [rcx+10h]
0x1400361d2  call    WPP_SF_S
0x1400361d7  test    sil, 4
0x1400361db  jz      loc_14003675D
0x1400361e1  mov     rcx, [rbp+0D0h+var_110]; bstrString
0x1400361e5  and     esi, 0FFFFFFFBh
0x1400361e8  call    cs:__imp_SysFreeString
0x1400361ee  jmp     loc_14003675D
0x1400361f3  xor     edx, edx
0x1400361f5  mov     [rbp+0D0h+var_148], edx
0x1400361f8  cmp     edx, [r13+40h]
0x1400361fc  jnb     loc_1400366DD
0x140036202  mov     eax, edx
0x140036204  lea     r12, [r14+44h]
0x140036208  imul    r13, rax, 78h ; 'x'
0x14003620c  mov     rax, [rsp+1D0h+var_160]
0x140036211  mov     rcx, [rax+48h]
0x140036215  mov     [rbp+0D0h+var_C8], rcx
0x140036219  mov     rax, [rcx+r13]
0x14003621d  sub     rax, [r12]
0x140036221  jnz     short loc_14003622D
0x140036223  mov     rax, [rcx+r13+8]
0x140036228  sub     rax, [r12+8]
0x14003622d  test    rax, rax
0x140036230  jz      short loc_14003623B
0x140036232  mov     r13, [rsp+1D0h+var_160]
0x140036237  inc     edx
0x140036239  jmp     short loc_1400361F5
0x14003623b  test    byte ptr [rcx+r13+10h], 80h
0x140036241  jz      short loc_1400362B8
0x140036243  mov     rax, cs:WPP_GLOBAL_Control
0x14003624a  lea     rbx, WPP_GLOBAL_Control
0x140036251  cmp     rax, rbx
0x140036254  jz      short loc_140036290
0x140036256  test    byte ptr [rax+1Ch], 1
0x14003625a  jz      short loc_140036290
0x14003625c  cmp     byte ptr [rax+19h], 4
0x140036260  jb      short loc_140036290
0x140036262  mov     rdx, r12; struct _GUID *
0x140036265  lea     rcx, [rbp+0D0h+var_108]; this
0x140036269  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14003626e  mov     rcx, cs:WPP_GLOBAL_Control
0x140036275  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003627c  or      esi, 8
0x14003627f  mov     edx, 305h
0x140036284  mov     r9, [rax]
0x140036287  mov     rcx, [rcx+10h]
0x14003628b  call    WPP_SF_S
0x140036290  test    sil, 8
0x140036294  jz      short loc_1400362A3
0x140036296  mov     rcx, [rbp+0D0h+var_108]; bstrString
0x14003629a  and     esi, 0FFFFFFF7h
0x14003629d  call    cs:__imp_SysFreeString
0x1400362a3  mov     dword ptr [r14+16Ch], 6
0x1400362ae  mov     r13, [rsp+1D0h+var_160]
0x1400362b3  jmp     loc_1400366E4
0x1400362b8  lea     rbx, [rcx+60h]
0x1400362bc  add     rbx, r13
0x1400362bf  test    byte ptr [r14+54h], 10h
0x1400362c4  mov     [rbp+0D0h+var_120], rbx
0x1400362c8  jnz     loc_140036664
0x1400362ce  movups  xmm0, xmmword ptr [rcx+r13+50h]
0x1400362d4  mov     r8d, 10h; Size
0x1400362da  lea     rdx, GUID_NULL; Buf2
0x1400362e1  lea     rcx, [rbp+0D0h+Buf1]; Buf1
0x1400362e5  movdqu  [rbp+0D0h+Buf1], xmm0
  ... truncated ...
```
