# BuildStateInfo(_ASRFMT_STATE_INFO *)

- ea: `0x140025e3c`
- end: `0x140026c02`
- name: `?BuildStateInfo@@YAHPEAU_ASRFMT_STATE_INFO@@@Z`
- size: `3526`
- prototype: `__int64 __fastcall(struct _ASRFMT_STATE_INFO *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400d9fe0`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x140025abc`
- `0x140025b00`
- `0x140025e3c`
- `0x140026c08`
- `0x14003b0c0`
- `0x14003b160`
- `0x140045e70`
- `0x140056398`
- `0x14005b208`
- `0x14005b49c`
- `0x140091560`
- `0x1400916f0`
- `0x1400d257c`
- `0x1400d26c8`
- `0x1400d278c`
- `0x1400d27a8`
- `0x1400d28b4`
- `0x1400d299c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002621b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002621b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400264ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400266eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026976`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400260e0`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1400260e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400261f4`

## string_xrefs

- `0x140026bb9`: `::StringCchCopyN(ARRAY_COUNT_PARAM(szVolumeGuid), pMp->pVolumeGuid, cchGuid)`
- `0x140026b72`: `::StringCchCopy(ARRAY_COUNT_PARAM(szFsName), pMp->szFsName)`
- `0x140025ec8`: `ERROR_PRIVILEGE_NOT_HELD`
- `0x1400268ff`: `::StringCchCopyN(ARRAY_COUNT_PARAM(pNewVolume->szGuid), pMp->pVolumeGuid, pMp->cchVolumeGuid)`
- `0x1400268b3`: `::StringCchCopy(ARRAY_COUNT_PARAM(pNewVolume->szFsName), szFsName)`
- `0x140026b14`: `::StringCchCopy(ARRAY_COUNT_PARAM(szLabel), pMp->szLabel)`
- `0x140026677`: `::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szVolumeGuid), pMp->pVolumeGuid, pMp->cchVolumeGuid)`
- `0x14002684e`: `::StringCchCopy(ARRAY_COUNT_PARAM(pNewVolume->szLabel), szLabel)`
- `0x140026a5b`: `::StringCchCopyN(ARRAY_COUNT_PARAM(pNewVolume->szDosPath), pCurrentLink->pLink, pCurrentLink->cchLink)`
- `0x14002660e`: `::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szDevicePath), pMp->pDeviceName, pMp->cchDeviceName)`
- `0x140026788`: `::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szDosPath), pCurrentLink->pLink, pCurrentLink->cchLink)`

## pseudocode

```c
__int64 __fastcall BuildStateInfo(struct _ASRFMT_VOLUME_INFO **a1)
{
  unsigned int v1; // ebx
  struct _MOUNTMGR_MOUNT_POINTS *v2; // r13
  unsigned __int16 *v3; // rsi
  unsigned __int16 *v4; // rdi
  int v5; // r12d
  int v6; // r9d
  unsigned int v7; // r14d
  DWORD LastError; // r15d
  struct _DRIVE_LAYOUT_INFORMATION_EX *v9; // rcx
  int v10; // edx
  const char *v11; // rax
  DWORD v12; // r9d
  struct _ASRFMT_MOUNT_POINTS_INFO *v13; // rax
  unsigned __int16 *v14; // r11
  struct _ASRFMT_MOUNT_POINTS_INFO *v15; // r15
  struct _ASRFMT_MOUNT_POINTS_INFO *i; // r13
  WCHAR *v17; // rax
  unsigned __int64 v18; // rdi
  WCHAR *v19; // r8
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  WCHAR *v22; // rcx
  int IsInaccessibleSanVolume; // eax
  unsigned int v24; // r8d
  UINT DriveTypeW; // eax
  __int64 v26; // rsi
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rsi
  int v29; // eax
  unsigned int v30; // r11d
  int v31; // eax
  unsigned int v32; // r11d
  DWORD v33; // eax
  int v34; // edx
  unsigned __int16 *v36; // rax
  int v37; // eax
  unsigned int v38; // r11d
  int v39; // eax
  unsigned int v40; // r11d
  int v41; // eax
  unsigned int v42; // r11d
  int v43; // eax
  char v44; // al
  unsigned int v45; // eax
  int v46; // eax
  unsigned int v47; // r11d
  int v48; // eax
  unsigned int v49; // r11d
  __int64 v50; // rdi
  unsigned __int16 *v51; // rax
  int v52; // eax
  unsigned int v53; // r11d
  int v54; // eax
  unsigned int v55; // r11d
  int v56; // eax
  unsigned int v57; // r11d
  struct _ASRFMT_VOLUME_INFO **v58; // rcx
  DWORD v59; // eax
  int v60; // edx
  unsigned __int16 *v61; // rax
  int v62; // eax
  unsigned int v63; // r11d
  int v64; // eax
  unsigned int v65; // r11d
  int v66; // eax
  unsigned int v67; // r11d
  int v68; // eax
  unsigned int v69; // r11d
  struct _ASRFMT_VOLUME_INFO **v70; // rcx
  int v71; // eax
  int v72; // edx
  int v73; // eax
  int v74; // edx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v75; // rcx
  int v76; // edx
  int v77; // eax
  int v78; // eax
  int v79; // edx
  int v80; // eax
  int v81; // edx
  int v82; // eax
  int v83; // edx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v84; // rcx
  int v85; // edx
  int v86; // eax
  int v87; // eax
  int v88; // eax
  int v89; // eax
  unsigned int v90; // [rsp+20h] [rbp-E0h]
  unsigned int *v91; // [rsp+28h] [rbp-D8h]
  struct _MOUNTMGR_MOUNT_POINTS *MountPoints; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v93[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v94; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _ASRFMT_MOUNT_POINTS_INFO *v95; // [rsp+40h] [rbp-C0h] BYREF
  struct _ASRFMT_VOLUME_INFO **v96; // [rsp+48h] [rbp-B8h]
  WCHAR FileSystemNameBuffer[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR RootPathName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v99[256]; // [rsp+280h] [rbp+180h] BYREF

  v96 = a1;
  TraceFunctionEnter(L"BuildStateInfo");
  v1 = 0;
  v2 = 0;
  v95 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 17;
  if ( !(unsigned int)pAcquirePrivilege(17) || (v5 = 18, !(unsigned int)pAcquirePrivilege(18)) )
  {
    v6 = 1314;
    v7 = 0;
    LastError = 1314;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_44;
    }
    v10 = v5;
    v11 = "ERROR_PRIVILEGE_NOT_HELD";
    goto LABEL_5;
  }
  MountPoints = GetMountPoints();
  v2 = MountPoints;
  if ( !MountPoints )
  {
    v7 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        19,
        (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
        v12,
        "GetLastError( )");
    }
    goto LABEL_44;
  }
  v13 = (struct _ASRFMT_MOUNT_POINTS_INFO *)ASR_ALLOC(0x448u);
  v14 = 0;
  v95 = v13;
  if ( !v13 )
  {
    v6 = 14;
    v7 = 0;
    LastError = 14;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_44;
    }
    v10 = 20;
    v11 = "pMpInfoList";
LABEL_5:
    WPP_SF_Ds(
      *(_QWORD *)v9->Gpt.DiskId.Data4,
      v10,
      (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
      v6,
      v11);
    goto LABEL_44;
  }
  v7 = 1;
  LastError = 0;
  if ( *((_DWORD *)MountPoints + 1) )
  {
    v15 = v13;
    do
    {
      AddSymbolicLink(
        v15,
        (unsigned __int16 *)((char *)MountPoints + *((unsigned int *)MountPoints + 6 * v1 + 6)),
        *((_WORD *)MountPoints + 12 * v1 + 14) >> 1,
        (unsigned __int16 *)((char *)MountPoints + *((unsigned int *)MountPoints + 6 * v1 + 2)),
        *((_WORD *)MountPoints + 12 * v1 + 6) >> 1,
        v91);
      ++v1;
    }
    while ( v1 < *((_DWORD *)MountPoints + 1) );
    v13 = v95;
    LastError = 0;
    v14 = 0;
  }
  for ( i = v13; ; i = *(struct _ASRFMT_MOUNT_POINTS_INFO **)i )
  {
    v3 = v14;
    v4 = v14;
    if ( !i )
      goto LABEL_43;
    if ( *((unsigned __int16 **)i + 1) == v14 )
      continue;
    v17 = (WCHAR *)*((_QWORD *)i + 2);
    if ( !v17 )
      continue;
    v18 = *((unsigned __int16 *)i + 23);
    v19 = RootPathName;
    v20 = v18;
    v94 = (unsigned int)v14;
    v21 = 261;
    do
    {
      if ( !v20 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v20;
      --v21;
    }
    while ( v21 );
    v22 = v19 - 1;
    if ( v21 )
      v22 = v19;
    *v22 = (unsigned __int16)v14;
    if ( !v21 )
      break;
    RootPathName[1] = 92;
    IsInaccessibleSanVolume = AsrfmtpIsInaccessibleSanVolume(RootPathName);
    v14 = 0;
    if ( IsInaccessibleSanVolume )
      continue;
    RootPathName[v18] = 92;
    if ( 2 * (unsigned __int64)(unsigned int)(v18 + 1) >= 0x20A )
      _report_rangecheckfailure();
    RootPathName[(unsigned int)(v18 + 1)] = 0;
    DriveTypeW = 0;
    if ( *((_DWORD *)i + 12) || (DriveTypeW = GetDriveTypeW(RootPathName), v14 = 0, *((_DWORD *)i + 12)) )
    {
      if ( DriveTypeW == 3 )
      {
LABEL_55:
        v93[0] = 0;
        v43 = IsVirtualVolume(RootPathName, v93);
        v14 = 0;
        if ( !v43 )
        {
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x400000000LL) == 0 )
          {
            continue;
          }
          v44 = GetLastError();
          WPP_SF_SD(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            22,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            (unsigned int)RootPathName,
            v44);
          goto LABEL_59;
        }
        if ( v93[0] )
        {
          if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x400000000LL) == 0 )
          {
            continue;
          }
          WPP_SF_S(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            23,
            WPP_9804a34647793532e49666254d335394_Traceguids,
            RootPathName);
LABEL_59:
          v14 = 0;
          continue;
        }
      }
      if ( *((_DWORD *)i + 12) )
      {
        v46 = StringCchCopyW(FileSystemNameBuffer, 0x10u, (const unsigned __int16 *)i + 26);
        if ( v46 < 0 )
        {
          v7 = v47;
          LastError = WIN32_FROM_HRESULT((unsigned int)v46);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v88 = StringCchCopyW(FileSystemNameBuffer, 0x10u, (const unsigned __int16 *)i + 26);
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              24,
              (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
              v88,
              "::StringCchCopy(ARRAY_COUNT_PARAM(szFsName), pMp->szFsName)");
          }
          goto LABEL_155;
        }
        v48 = StringCchCopyW(v99, 0x100u, (const unsigned __int16 *)i + 287);
        if ( v48 < 0 )
        {
          v7 = v49;
          LastError = WIN32_FROM_HRESULT((unsigned int)v48);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v87 = StringCchCopyW(v99, 0x100u, (const unsigned __int16 *)i + 287);
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              25,
              (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
              v87,
              "::StringCchCopy(ARRAY_COUNT_PARAM(szLabel), pMp->szLabel)");
          }
          goto LABEL_155;
        }
        v45 = *((_DWORD *)i + 10);
      }
      else
      {
        GetVolumeDetails(RootPathName, FileSystemNameBuffer, v24, v99, v90, &v94);
        v45 = v94;
      }
      v50 = *((_QWORD *)i + 3);
      v94 = v45;
      if ( v50 )
      {
        while ( 1 )
        {
          v61 = (unsigned __int16 *)ASR_ALLOC(0xAB8u);
          v3 = v61;
          if ( !v61 )
            break;
          *(_QWORD *)v61 = 0;
          v62 = StringCchCopyNW(v61 + 6, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
          if ( v62 < 0 )
          {
            v7 = v63;
            LastError = WIN32_FROM_HRESULT((unsigned int)v62);
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v82 = StringCchCopyNW(v3 + 6, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
              v83 = 32;
              goto LABEL_128;
            }
            goto LABEL_80;
          }
          v64 = StringCchCopyNW(v3 + 70, 0x400u, *(const unsigned __int16 **)v50, *(unsigned __int16 *)(v50 + 8));
          if ( v64 < 0 )
          {
            v7 = v65;
            LastError = WIN32_FROM_HRESULT((unsigned int)v64);
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v86 = StringCchCopyNW(v3 + 70, 0x400u, *(const unsigned __int16 **)v50, *(unsigned __int16 *)(v50 + 8));
              WPP_SF_Ds(
                *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                33,
                (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
                v86,
                "::StringCchCopyN(ARRAY_COUNT_PARAM(pNewVolume->szDosPath), pCurrentLink->pLink, pCurrentLink->cchLink)");
            }
            goto LABEL_80;
          }
          v66 = StringCchCopyW(v3 + 1094, v65 + 16, FileSystemNameBuffer);
          if ( v66 < 0 )
          {
            v7 = v67;
            LastError = WIN32_FROM_HRESULT((unsigned int)v66);
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v80 = StringCchCopyW(v3 + 1094, 0x10u, FileSystemNameBuffer);
              v81 = 34;
              goto LABEL_124;
            }
            goto LABEL_80;
          }
          v68 = StringCchCopyW(v3 + 1110, 0x100u, v99);
          if ( v68 < 0 )
          {
            v7 = v69;
            LastError = WIN32_FROM_HRESULT((unsigned int)v68);
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v78 = StringCchCopyW(v3 + 1110, 0x100u, v99);
              v79 = 35;
              goto LABEL_120;
            }
            goto LABEL_80;
          }
          v70 = v96;
          *((_DWORD *)v3 + 683) = v94;
          if ( !(unsigned int)AddSortedVolumeInfo(v70, (struct _ASRFMT_VOLUME_INFO *)v3) )
          {
            v7 = (unsigned int)v14;
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
            {
              v59 = GetLastError();
              v60 = 36;
              goto LABEL_79;
            }
            goto LABEL_80;
          }
          v50 = *(_QWORD *)(v50 + 16);
          if ( !v50 )
            goto LABEL_60;
        }
        v7 = 0;
        LastError = 14;
        v84 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v85 = 31;
          goto LABEL_132;
        }
LABEL_133:
        v4 = 0;
        goto LABEL_43;
      }
      v51 = (unsigned __int16 *)ASR_ALLOC(0xAB8u);
      v3 = v51;
      if ( !v51 )
      {
        v7 = 0;
        LastError = 14;
        v84 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v85 = 26;
LABEL_132:
          WPP_SF_Ds(
            *(_QWORD *)v84->Gpt.DiskId.Data4,
            v85,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            14,
            "pNewVolume");
        }
        goto LABEL_133;
      }
      *(_QWORD *)v51 = 0;
      v52 = StringCchCopyNW(v51 + 6, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
      if ( v52 < 0 )
      {
        v7 = v53;
        LastError = WIN32_FROM_HRESULT((unsigned int)v52);
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v82 = StringCchCopyNW(v3 + 6, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
          v83 = 27;
LABEL_128:
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            v83,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            v82,
            "::StringCchCopyN(ARRAY_COUNT_PARAM(pNewVolume->szGuid), pMp->pVolumeGuid, pMp->cchVolumeGuid)");
        }
        goto LABEL_80;
      }
      v54 = StringCchCopyW(v3 + 1094, v53 + 16, FileSystemNameBuffer);
      if ( v54 < 0 )
      {
        v7 = v55;
        LastError = WIN32_FROM_HRESULT((unsigned int)v54);
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v80 = StringCchCopyW(v3 + 1094, 0x10u, FileSystemNameBuffer);
          v81 = 28;
LABEL_124:
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            v81,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            v80,
            "::StringCchCopy(ARRAY_COUNT_PARAM(pNewVolume->szFsName), szFsName)");
        }
        goto LABEL_80;
      }
      v56 = StringCchCopyW(v3 + 1110, 0x100u, v99);
      if ( v56 < 0 )
      {
        v7 = v57;
        LastError = WIN32_FROM_HRESULT((unsigned int)v56);
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v78 = StringCchCopyW(v3 + 1110, 0x100u, v99);
          v79 = 29;
LABEL_120:
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            v79,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            v78,
            "::StringCchCopy(ARRAY_COUNT_PARAM(pNewVolume->szLabel), szLabel)");
        }
        goto LABEL_80;
      }
      v58 = v96;
      *((_DWORD *)v3 + 683) = v94;
      if ( !(unsigned int)AddSortedVolumeInfo(v58, (struct _ASRFMT_VOLUME_INFO *)v3) )
      {
        v7 = (unsigned int)v14;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v59 = GetLastError();
          v60 = 30;
LABEL_79:
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            v60,
            (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
            v59,
            "GetLastError( )");
        }
        goto LABEL_80;
      }
      continue;
    }
    if ( DriveTypeW == 3 )
      goto LABEL_55;
    if ( !DriveTypeW )
      continue;
    v26 = *((_QWORD *)i + 3);
    if ( v26 )
    {
      while ( 1 )
      {
        v36 = (unsigned __int16 *)ASR_ALLOC(0x1090u);
        v4 = v36;
        if ( !v36 )
          break;
        *(_QWORD *)v36 = 0;
        v37 = StringCchCopyNW(v36 + 1030, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
        if ( v37 < 0 )
        {
          v7 = v38;
          LastError = WIN32_FROM_HRESULT((unsigned int)v37);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v73 = StringCchCopyNW(v4 + 1030, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
            v74 = 42;
            goto LABEL_96;
          }
          goto LABEL_42;
        }
        v39 = StringCchCopyNW(v4 + 1094, 0x400u, *(const unsigned __int16 **)v26, *(unsigned __int16 *)(v26 + 8));
        if ( v39 < 0 )
        {
          v7 = v40;
          LastError = WIN32_FROM_HRESULT((unsigned int)v39);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v77 = StringCchCopyNW(v4 + 1094, 0x400u, *(const unsigned __int16 **)v26, *(unsigned __int16 *)(v26 + 8));
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              43,
              (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
              v77,
              "::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szDosPath), pCurrentLink->pLink, pCurrentLink->cchLink)");
          }
          goto LABEL_42;
        }
        v41 = StringCchCopyNW(v4 + 6, 0x400u, *((const unsigned __int16 **)i + 1), *((unsigned __int16 *)i + 22));
        if ( v41 < 0 )
        {
          v7 = v42;
          LastError = WIN32_FROM_HRESULT((unsigned int)v41);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v71 = StringCchCopyNW(v4 + 6, 0x400u, *((const unsigned __int16 **)i + 1), *((unsigned __int16 *)i + 22));
            v72 = 44;
            goto LABEL_92;
          }
          goto LABEL_42;
        }
        if ( !(unsigned int)AddSortedVolumeInfo(v96 + 2, (struct _ASRFMT_VOLUME_INFO *)v4) )
        {
          v7 = (unsigned int)v14;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v33 = GetLastError();
            v34 = 45;
            goto LABEL_41;
          }
          goto LABEL_42;
        }
        v26 = *(_QWORD *)(v26 + 16);
        if ( !v26 )
          goto LABEL_60;
      }
      v7 = 0;
      LastError = 14;
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v76 = 41;
        goto LABEL_100;
      }
      goto LABEL_101;
    }
    v27 = (unsigned __int16 *)ASR_ALLOC(0x1090u);
    v4 = v27;
    if ( !v27 )
    {
      v7 = 0;
      LastError = 14;
      v75 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v76 = 37;
LABEL_100:
        WPP_SF_Ds(
          *(_QWORD *)v75->Gpt.DiskId.Data4,
          v76,
          (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
          14,
          "pNewMedia");
      }
LABEL_101:
      v3 = 0;
      goto LABEL_43;
    }
    *(_QWORD *)v27 = 0;
    v28 = v27 + 1030;
    v29 = StringCchCopyNW(v27 + 1030, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
    if ( v29 < 0 )
    {
      v7 = v30;
      LastError = WIN32_FROM_HRESULT((unsigned int)v29);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v73 = StringCchCopyNW(v28, 0x40u, *((const unsigned __int16 **)i + 2), *((unsigned __int16 *)i + 23));
        v74 = 38;
LABEL_96:
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          v74,
          (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
          v73,
          "::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szVolumeGuid), pMp->pVolumeGuid, pMp->cchVolumeGuid)");
      }
      goto LABEL_42;
    }
    v31 = StringCchCopyNW(v4 + 6, 0x400u, *((const unsigned __int16 **)i + 1), *((unsigned __int16 *)i + 22));
    if ( v31 < 0 )
    {
      v7 = v32;
      LastError = WIN32_FROM_HRESULT((unsigned int)v31);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v71 = StringCchCopyNW(v4 + 6, 0x400u, *((const unsigned __int16 **)i + 1), *((unsigned __int16 *)i + 22));
        v72 = 39;
LABEL_92:
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          v72,
          (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
          v71,
          "::StringCchCopyN(ARRAY_COUNT_PARAM(pNewMedia->szDevicePath), pMp->pDeviceName, pMp->cchDeviceName)");
      }
      goto LABEL_42;
    }
    if ( !(unsigned int)AddSortedVolumeInfo(v96 + 2, (struct _ASRFMT_VOLUME_INFO *)v4) )
    {
      v7 = (unsigned int)v14;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v33 = GetLastError();
        v34 = 40;
LABEL_41:
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          v34,
          (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
          v33,
          "GetLastError( )");
      }
LABEL_42:
      v3 = 0;
      goto LABEL_43;
    }
LABEL_60:
    ;
  }
  v7 = (unsigned int)v14;
  LastError = WIN32_FROM_HRESULT(2147942522LL);
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v89 = StringCchCopyNW(RootPathName, 0x105u, *((const unsigned __int16 **)i + 2), v18);
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      21,
      (unsigned int)WPP_9804a34647793532e49666254d335394_Traceguids,
      v89,
      "::StringCchCopyN(ARRAY_COUNT_PARAM(szVolumeGuid), pMp->pVolumeGuid, cchGuid)");
  }
LABEL_155:
  v3 = 0;
LABEL_80:
  v4 = 0;
LABEL_43:
  v2 = MountPoints;
LABEL_44:
  CoTaskMemFree(v3);
  CoTaskMemFree(v4);
  CoTaskMemFree(v2);
  if ( v95 )
    FreeMpInfo(&v95);
  TraceFunctionExit(L"BuildStateInfo");
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x140025e3c  push    rbp
0x140025e3e  push    rbx
0x140025e3f  push    rsi
0x140025e40  push    rdi
0x140025e41  push    r12
0x140025e43  push    r13
0x140025e45  push    r14
0x140025e47  push    r15
0x140025e49  lea     rbp, [rsp-398h]
0x140025e51  sub     rsp, 498h
0x140025e58  mov     rax, cs:__security_cookie
0x140025e5f  xor     rax, rsp
0x140025e62  mov     [rbp+3D0h+var_50], rax
0x140025e69  mov     [rsp+4D0h+var_488], rcx
0x140025e6e  lea     rcx, aBuildstateinfo; "BuildStateInfo"
0x140025e75  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140025e7a  xor     ebx, ebx
0x140025e7c  mov     r13d, ebx
0x140025e7f  mov     [rsp+4D0h+var_490], rbx
0x140025e84  mov     esi, ebx
0x140025e86  mov     edi, ebx
0x140025e88  lea     r12d, [rbx+11h]
0x140025e8c  mov     ecx, r12d; int
0x140025e8f  call    ?pAcquirePrivilege@@YAHJ@Z; pAcquirePrivilege(long)
0x140025e94  test    eax, eax
0x140025e96  jnz     short loc_140025EE9
0x140025e98  mov     r9d, 522h
0x140025e9e  mov     r14d, ebx
0x140025ea1  mov     r15d, r9d
0x140025ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140025eab  lea     rbx, WPP_GLOBAL_Control
0x140025eb2  cmp     rcx, rbx
0x140025eb5  jz      loc_1400261DF
0x140025ebb  test    byte ptr [rcx+1Ch], 8
0x140025ebf  jz      loc_1400261DF
0x140025ec5  mov     edx, r12d
0x140025ec8  lea     rax, aErrorPrivilege; "ERROR_PRIVILEGE_NOT_HELD"
0x140025ecf  mov     qword ptr [rsp+4D0h+var_4B0], rax
0x140025ed4  mov     rcx, [rcx+10h]
0x140025ed8  lea     r8, WPP_9804a34647793532e49666254d335394_Traceguids
0x140025edf  call    WPP_SF_Ds
0x140025ee4  jmp     loc_1400261DF
0x140025ee9  mov     r12d, 12h
0x140025eef  mov     ecx, r12d; int
0x140025ef2  call    ?pAcquirePrivilege@@YAHJ@Z; pAcquirePrivilege(long)
0x140025ef7  test    eax, eax
0x140025ef9  jnz     short loc_140025F1A
0x140025efb  mov     r9d, 522h
0x140025f01  mov     r14d, ebx
0x140025f04  mov     r15d, r9d
0x140025f07  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f0e  lea     rbx, WPP_GLOBAL_Control
0x140025f15  cmp     rcx, rbx
0x140025f18  jmp     short loc_140025EB5
0x140025f1a  call    ?GetMountPoints@@YAPEAU_MOUNTMGR_MOUNT_POINTS@@XZ; GetMountPoints(void)
0x140025f1f  mov     [rsp+4D0h+var_4A0], rax
0x140025f24  mov     r13, rax
0x140025f27  test    rax, rax
0x140025f2a  jnz     short loc_140025F7E
0x140025f2c  mov     r14d, ebx
0x140025f2f  call    cs:__imp_GetLastError
0x140025f35  mov     r15d, eax
0x140025f38  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f3f  lea     rbx, WPP_GLOBAL_Control
0x140025f46  cmp     rcx, rbx
0x140025f49  jz      loc_1400261DF
0x140025f4f  test    byte ptr [rcx+1Ch], 8
0x140025f53  jz      loc_1400261DF
0x140025f59  call    cs:__imp_GetLastError
0x140025f5f  lea     rcx, aGetlasterror; "GetLastError( )"
0x140025f66  mov     r9d, eax
0x140025f69  mov     qword ptr [rsp+4D0h+var_4B0], rcx
0x140025f6e  lea     edx, [r13+13h]
0x140025f72  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f79  jmp     loc_140025ED4
0x140025f7e  mov     ecx, 448h; Size
0x140025f83  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x140025f88  xor     r11d, r11d
0x140025f8b  mov     [rsp+4D0h+var_490], rax
0x140025f90  test    rax, rax
0x140025f93  jz      loc_140026BC5
0x140025f99  lea     r14d, [r11+1]
0x140025f9d  mov     r15d, r11d
0x140025fa0  mov     rdi, r13
0x140025fa3  cmp     [r13+4], r11d
0x140025fa7  jbe     short loc_140025FF3
0x140025fa9  mov     r15, rax
0x140025fac  mov     eax, ebx
0x140025fae  lea     rcx, [rax+rax*2]
0x140025fb2  movzx   eax, word ptr [rdi+rcx*8+0Ch]
0x140025fb7  mov     r9d, [rdi+rcx*8+8]
0x140025fbc  movzx   r8d, word ptr [rdi+rcx*8+1Ch]
0x140025fc2  add     r9, rdi; unsigned __int16 *
0x140025fc5  mov     edx, [rdi+rcx*8+18h]
0x140025fc9  mov     rcx, r15; struct _ASRFMT_MOUNT_POINTS_INFO *
0x140025fcc  shr     ax, 1
0x140025fcf  add     rdx, rdi; unsigned __int16 *
0x140025fd2  shr     r8w, 1; unsigned __int16
0x140025fd6  mov     word ptr [rsp+4D0h+var_4B0], ax; unsigned int
0x140025fdb  call    ?AddSymbolicLink@@YAHPEAU_ASRFMT_MOUNT_POINTS_INFO@@PEAGG1GPEAX@Z; AddSymbolicLink(_ASRFMT_MOUNT_POINTS_INFO *,ushort *,ushort,ushort *,ushort,void *)
0x140025fe0  add     ebx, r14d
0x140025fe3  cmp     ebx, [rdi+4]
0x140025fe6  jb      short loc_140025FAC
0x140025fe8  mov     rax, [rsp+4D0h+var_490]
0x140025fed  mov     r15d, esi
0x140025ff0  xor     r11d, r11d
0x140025ff3  mov     r13, rax
0x140025ff6  lea     rbx, WPP_GLOBAL_Control
0x140025ffd  lea     r12, WPP_9804a34647793532e49666254d335394_Traceguids
0x140026004  mov     r10d, 5Ch ; '\'
0x14002600a  mov     rsi, r11
0x14002600d  mov     rdi, r11
0x140026010  test    r13, r13
0x140026013  jz      loc_1400261DA
0x140026019  cmp     [r13+8], r11
0x14002601d  jz      loc_140026355
0x140026023  mov     rax, [r13+10h]
0x140026027  test    rax, rax
0x14002602a  jz      loc_140026355
0x140026030  movzx   edi, word ptr [r13+2Eh]
0x140026035  lea     r8, [rsp+4D0h+RootPathName]
0x14002603a  mov     r9d, edi
0x14002603d  mov     [rsp+4D0h+var_494], r11d
0x140026042  mov     edx, 105h
0x140026047  test    r9, r9
0x14002604a  jz      short loc_140026068
0x14002604c  movzx   ecx, word ptr [rax]
0x14002604f  test    cx, cx
0x140026052  jz      short loc_140026068
0x140026054  mov     [r8], cx
0x140026058  add     rax, 2
0x14002605c  add     r8, 2
0x140026060  sub     r9, r14
0x140026063  sub     rdx, r14
0x140026066  jnz     short loc_140026047
0x140026068  test    rdx, rdx
0x14002606b  lea     rcx, [r8-2]
0x14002606f  mov     rax, rdx
0x140026072  cmovnz  rcx, r8
0x140026076  neg     rax
0x140026079  mov     [rcx], r11w
0x14002607d  sbb     ecx, ecx
0x14002607f  not     ecx
0x140026081  and     ecx, 8007007Ah
0x140026087  test    rdx, rdx
0x14002608a  jz      loc_140026B81
0x140026090  lea     rcx, [rsp+4D0h+RootPathName]; unsigned __int16 *
0x140026095  mov     [rsp+4D0h+var_45E], r10w
0x14002609b  call    ?AsrfmtpIsInaccessibleSanVolume@@YAHPEBG@Z; AsrfmtpIsInaccessibleSanVolume(ushort const *)
0x1400260a0  xor     r11d, r11d
0x1400260a3  lea     r10d, [r11+5Ch]
0x1400260a7  test    eax, eax
0x1400260a9  jnz     loc_140026355
0x1400260af  lea     ecx, [rdi+1]
0x1400260b2  mov     [rsp+rdi*2+4D0h+RootPathName], r10w
0x1400260b8  add     rcx, rcx
0x1400260bb  cmp     rcx, 20Ah
0x1400260c2  jnb     loc_140026B7B
0x1400260c8  mov     [rsp+rcx+4D0h+RootPathName], r11w
0x1400260ce  mov     eax, r11d
0x1400260d1  cmp     [r13+30h], r11d
0x1400260d5  jnz     loc_1400262EF
0x1400260db  lea     rcx, [rsp+4D0h+RootPathName]; lpRootPathName
0x1400260e0  call    cs:__imp_GetDriveTypeW
0x1400260e6  xor     r11d, r11d
0x1400260e9  lea     r10d, [r11+5Ch]
0x1400260ed  cmp     [r13+30h], r11d
0x1400260f1  jnz     loc_1400262EF
0x1400260f7  cmp     eax, 3
0x1400260fa  jz      loc_1400262F8
0x140026100  test    eax, eax
0x140026102  jz      loc_140026355
0x140026108  mov     rsi, [r13+18h]
0x14002610c  test    rsi, rsi
0x14002610f  jnz     loc_140026250
0x140026115  mov     ecx, 1090h; Size
0x14002611a  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14002611f  xor     r11d, r11d
0x140026122  mov     rdi, rax
0x140026125  test    rax, rax
0x140026128  jz      loc_140026680
0x14002612e  mov     [rax], r11
0x140026131  lea     rsi, [rax+80Ch]
0x140026138  movzx   r9d, word ptr [r13+2Eh]; unsigned __int64
0x14002613d  lea     edx, [r11+40h]; unsigned __int64
0x140026141  mov     r8, [r13+10h]; unsigned __int16 *
0x140026145  mov     rcx, rsi; unsigned __int16 *
0x140026148  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14002614d  test    eax, eax
0x14002614f  js      loc_140026635
0x140026155  movzx   r9d, word ptr [r13+2Ch]; unsigned __int64
0x14002615a  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x14002615e  mov     r8, [r13+8]; unsigned __int16 *
0x140026162  mov     edx, 400h; unsigned __int64
0x140026167  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14002616c  test    eax, eax
0x14002616e  js      loc_1400265CB
0x140026174  mov     rcx, [rsp+4D0h+var_488]
0x140026179  mov     rdx, rdi; struct _ASRFMT_VOLUME_INFO *
0x14002617c  add     rcx, 10h; struct _ASRFMT_VOLUME_INFO **
0x140026180  call    ?AddSortedVolumeInfo@@YAHPEAPEAU_ASRFMT_VOLUME_INFO@@PEAU1@@Z; AddSortedVolumeInfo(_ASRFMT_VOLUME_INFO * *,_ASRFMT_VOLUME_INFO *)
0x140026185  test    eax, eax
0x140026187  jnz     loc_14002634F
0x14002618d  mov     r14d, r11d
0x140026190  call    cs:__imp_GetLastError
0x140026196  mov     r15d, eax
0x140026199  mov     rax, cs:WPP_GLOBAL_Control
0x1400261a0  cmp     rax, rbx
0x1400261a3  jz      short loc_1400261D8
0x1400261a5  test    byte ptr [rax+1Ch], 8
0x1400261a9  jz      short loc_1400261D8
0x1400261ab  call    cs:__imp_GetLastError
0x1400261b1  mov     edx, 28h ; '('
0x1400261b6  lea     rcx, aGetlasterror; "GetLastError( )"
0x1400261bd  mov     r9d, eax
0x1400261c0  mov     qword ptr [rsp+4D0h+var_4B0], rcx
0x1400261c5  mov     r8, r12
0x1400261c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261cf  mov     rcx, [rcx+10h]
0x1400261d3  call    WPP_SF_Ds
0x1400261d8  xor     esi, esi
0x1400261da  mov     r13, [rsp+4D0h+var_4A0]
0x1400261df  mov     rcx, rsi; pv
0x1400261e2  call    cs:__imp_CoTaskMemFree
0x1400261e8  mov     rcx, rdi; pv
0x1400261eb  call    cs:__imp_CoTaskMemFree
0x1400261f1  mov     rcx, r13; pv
0x1400261f4  call    cs:__imp_CoTaskMemFree
0x1400261fa  cmp     [rsp+4D0h+var_490], 0
0x140026200  jz      short loc_14002620C
0x140026202  lea     rcx, [rsp+4D0h+var_490]; struct _ASRFMT_MOUNT_POINTS_INFO **
0x140026207  call    ?FreeMpInfo@@YAXPEAPEAU_ASRFMT_MOUNT_POINTS_INFO@@@Z; FreeMpInfo(_ASRFMT_MOUNT_POINTS_INFO * *)
0x14002620c  lea     rcx, aBuildstateinfo; "BuildStateInfo"
0x140026213  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140026218  mov     ecx, r15d; dwErrCode
0x14002621b  call    cs:__imp_SetLastError
0x140026221  mov     eax, r14d
0x140026224  mov     rcx, [rbp+3D0h+var_50]
0x14002622b  xor     rcx, rsp; StackCookie
0x14002622e  call    __security_check_cookie
0x140026233  add     rsp, 498h
0x14002623a  pop     r15
0x14002623c  pop     r14
0x14002623e  pop     r13
0x140026240  pop     r12
0x140026242  pop     rdi
0x140026243  pop     rsi
0x140026244  pop     rbx
0x140026245  pop     rbp
0x140026246  retn
0x140026247  test    rsi, rsi
0x14002624a  jz      loc_14002634F
0x140026250  mov     ecx, 1090h; Size
0x140026255  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14002625a  xor     r11d, r11d
0x14002625d  mov     rdi, rax
0x140026260  test    rax, rax
0x140026263  jz      loc_1400267DF
0x140026269  mov     [rax], r11
0x14002626c  lea     rcx, [rax+80Ch]; unsigned __int16 *
0x140026273  movzx   r9d, word ptr [r13+2Eh]; unsigned __int64
0x140026278  lea     edx, [r11+40h]; unsigned __int64
0x14002627c  mov     r8, [r13+10h]; unsigned __int16 *
0x140026280  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140026285  test    eax, eax
0x140026287  js      loc_140026794
0x14002628d  movzx   r9d, word ptr [rsi+8]; unsigned __int64
0x140026292  lea     rcx, [rdi+88Ch]; unsigned __int16 *
0x140026299  mov     r8, [rsi]; unsigned __int16 *
0x14002629c  mov     edx, 400h; unsigned __int64
0x1400262a1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400262a6  test    eax, eax
0x1400262a8  js      loc_140026743
0x1400262ae  movzx   r9d, word ptr [r13+2Ch]; unsigned __int64
0x1400262b3  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x1400262b7  mov     r8, [r13+8]; unsigned __int16 *
0x1400262bb  mov     edx, 400h; unsigned __int64
0x1400262c0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400262c5  test    eax, eax
0x1400262c7  js      loc_1400266FB
0x1400262cd  mov     rcx, [rsp+4D0h+var_488]
0x1400262d2  mov     rdx, rdi; struct _ASRFMT_VOLUME_INFO *
0x1400262d5  add     rcx, 10h; struct _ASRFMT_VOLUME_INFO **
0x1400262d9  call    ?AddSortedVolumeInfo@@YAHPEAPEAU_ASRFMT_VOLUME_INFO@@PEAU1@@Z; AddSortedVolumeInfo(_ASRFMT_VOLUME_INFO * *,_ASRFMT_VOLUME_INFO *)
0x1400262de  test    eax, eax
0x1400262e0  jz      loc_1400266C5
0x1400262e6  mov     rsi, [rsi+10h]
0x1400262ea  jmp     loc_140026247
0x1400262ef  cmp     eax, 3
0x1400262f2  jnz     loc_14002638F
0x1400262f8  lea     rdx, [rsp+4D0h+var_498]; unsigned __int8 *
0x1400262fd  mov     [rsp+4D0h+var_498], r11b
0x140026302  lea     rcx, [rsp+4D0h+RootPathName]; unsigned __int16 *
0x140026307  call    ?IsVirtualVolume@@YAHPEBGPEAE@Z; IsVirtualVolume(ushort const *,uchar *)
0x14002630c  xor     r11d, r11d
0x14002630f  test    eax, eax
0x140026311  jnz     short loc_14002635E
0x140026313  mov     rax, cs:WPP_GLOBAL_Control
0x14002631a  cmp     rax, rbx
0x14002631d  jz      short loc_14002634F
  ... truncated ...
```
