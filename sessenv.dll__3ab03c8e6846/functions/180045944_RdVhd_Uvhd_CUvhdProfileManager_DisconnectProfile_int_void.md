# RdVhd::Uvhd::CUvhdProfileManager::DisconnectProfile(int,void *)

- ea: `0x180045944`
- end: `0x1800462f5`
- name: `?DisconnectProfile@CUvhdProfileManager@Uvhd@RdVhd@@QEAAJHPEAX@Z`
- size: `2481`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdProfileManager *__hidden this, int, void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180044c70`
- `0x1800462fc`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18001a8d0`
- `0x180042ff4`
- `0x180045530`
- `0x18004568c`
- `0x180045944`
- `0x1800468ec`
- `0x180046ffc`
- `0x180048180`
- `0x180048450`
- `0x1800487b8`
- `0x180048844`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045a02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045a02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045a3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045a5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045a5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180045997`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800462c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180045997`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800462c8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180045ab7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180045ab7`

## string_xrefs

- `0x180045cc1`: `DeleteUsrClassLocalSettingRegKeyWithRetry() for user %s return 0x%08x.`
- `0x180045b19`: `DisconnectProfile(): Profile is in use! SID: %s`
- `0x180045d9f`: `Found UVHD volume mount point at '%s'`
- `0x180045e05`: `Failed to obtain UVHD disk number for mount point: %s. Ignoring the error.`
- `0x180045efd`: `Could not detach UVHD disk on Logon. Possibly recovering from hard-reboot. Ignoring. SID: %s`
- `0x18004602a`: `BackupUserProfile() FAILED; User SID: %s`
- `0x1800461c0`: `bSymLinkProfile() FAILED; User SID: %s`
- `0x180046218`: `SymLink profile for user %s, don't delete profile`
- `0x180046129`: `Delete profile for user %s`
- `0x180046257`: `Local user profile exepected to exist, but does not; SID: %s`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdProfileManager::DisconnectProfile(
        RdVhd::Uvhd::CUvhdProfileManager *this,
        int a2,
        void *a3)
{
  void *v3; // rbx
  unsigned int v5; // r14d
  unsigned int v6; // esi
  char *v7; // r12
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64, __int64, int *); // r10
  __int64 v10; // r11
  int v11; // eax
  int MountedUvhdMountPoint; // edi
  RdVhd::Uvhd::CUvhdDiskManager *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rax
  int v21; // edx
  int v22; // r8d
  _QWORD *v23; // rdi
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // r11
  __int64 v27; // r10
  const unsigned __int16 *v28; // rax
  __int64 v29; // rax
  int v30; // r10d
  const unsigned __int16 *v31; // rax
  struct RdVhd::Uvhd::IDirectoryHelper *v32; // r10
  __int64 v33; // rax
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // r9
  __int64 v36; // rax
  int (__fastcall *v37)(__int64, __int64, DWORD *); // r10
  __int64 v38; // r11
  __int64 v39; // rax
  int v40; // r10d
  int v41; // eax
  char v42; // r10
  const unsigned __int16 *v43; // rax
  int v44; // r10d
  int v45; // eax
  const unsigned __int16 *v46; // rax
  unsigned int v47; // r10d
  int v48; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // r10
  __int64 (__fastcall *v54)(__int64, __int64, __int64, void ***); // r11
  __int64 v55; // rax
  const unsigned __int16 *v56; // rax
  const unsigned __int16 *v57; // r9
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 (__fastcall *v60)(__int64, __int64); // r10
  __int64 v61; // r11
  const unsigned __int16 *v62; // rax
  RdVhd::Uvhd::CUvhdProfileManager *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  int v68; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-99h]
  int v71; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-81h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-79h] BYREF
  void *v74; // [rsp+48h] [rbp-71h] BYREF
  void **v75; // [rsp+50h] [rbp-69h] BYREF
  int v76; // [rsp+58h] [rbp-61h]
  __int64 v77; // [rsp+5Ch] [rbp-5Dh]
  int v78; // [rsp+64h] [rbp-55h]
  __int64 v79; // [rsp+68h] [rbp-51h]
  int v80; // [rsp+70h] [rbp-49h]
  HKEY hKey; // [rsp+78h] [rbp-41h] BYREF
  void **v82; // [rsp+80h] [rbp-39h] BYREF
  int v83; // [rsp+88h] [rbp-31h]
  __int64 v84; // [rsp+8Ch] [rbp-2Dh]
  int v85; // [rsp+94h] [rbp-25h]
  __int64 v86; // [rsp+98h] [rbp-21h]
  int v87; // [rsp+A0h] [rbp-19h]
  void **v88; // [rsp+A8h] [rbp-11h] BYREF
  int v89; // [rsp+B0h] [rbp-9h]
  __int64 v90; // [rsp+B4h] [rbp-5h]
  int v91; // [rsp+BCh] [rbp+3h]
  __int64 v92; // [rsp+C0h] [rbp+7h]
  int v93; // [rsp+C8h] [rbp+Fh]
  int v94; // [rsp+120h] [rbp+67h] BYREF
  int v95; // [rsp+128h] [rbp+6Fh]
  void *v96; // [rsp+130h] [rbp+77h]
  DWORD Type; // [rsp+138h] [rbp+7Fh] BYREF

  v96 = a3;
  v95 = a2;
  v84 = 128;
  v3 = 0;
  v86 = 0;
  v74 = 0;
  v85 = 0;
  v87 = 0x8000000;
  v83 = 0;
  v82 = &CPathString::`vftable';
  GetTickCount();
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this) )
    goto LABEL_121;
  v80 = 0x8000000;
  v94 = 0;
  v71 = 0;
  v77 = 128;
  v79 = 0;
  v5 = 2000;
  v78 = 0;
  v6 = 0;
  v76 = 0;
  v75 = &CPathString::`vftable';
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"RDUPDProfileUnloadWaitTime", 0, &Type, Data, cbData) && Type == 4 )
      v5 = 1000 * *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  *(_QWORD *)cbData = (char *)this + 16;
  v7 = (char *)this + 16;
  while ( v6 <= v5 )
  {
    v7 = (char *)this + 16;
    v8 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    v11 = v9(v10, v8, &v94);
    MountedUvhdMountPoint = v11;
    if ( v11 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 92;
        v15 = (unsigned int)v11;
        goto LABEL_16;
      }
LABEL_17:
      CPathString::~CPathString((CPathString *)&v75);
      goto LABEL_122;
    }
    if ( !v94 )
      goto LABEL_23;
    Sleep(0x64u);
    v6 += 100;
  }
  if ( v94 )
  {
    v16 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    MountedUvhdMountPoint = -799211350;
    _TraceNrmRdvVmEx(L"UVHD", -799211350, L"DisconnectProfile(): Profile is in use! SID: %s", v16);
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
      WPP_SF_LSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v6, v17, 170);
    }
    goto LABEL_17;
  }
LABEL_23:
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v23 = v7;
      *(_QWORD *)cbData = v7;
      goto LABEL_29;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v20 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v6, v20);
      v23 = (_QWORD *)((char *)this + 16);
      goto LABEL_29;
    }
  }
  v23 = (_QWORD *)((char *)this + 16);
  *(_QWORD *)cbData = (char *)this + 16;
LABEL_29:
  if ( v96 )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD, void *, void ***))(*(_QWORD *)*v23 + 24LL))(*v23, v96, &v82);
  }
  else
  {
    v25 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void ***))(v26 + 16))(v27, v25, 1, &v82);
  }
  MountedUvhdMountPoint = v24;
  if ( (_WORD)v24 == 2 )
  {
    MountedUvhdMountPoint = 1;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids);
    }
    goto LABEL_17;
  }
  if ( v24 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v14 = 96;
    goto LABEL_42;
  }
  v28 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v82);
  RdVhd::Uvhd::CUvhdProfileManager::DeleteUsrClassLocalSettingRegKeyWithRetry(this, v28);
  v29 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
  LODWORD(phkResult) = v30;
  _TraceNrmRdvVmEx(
    L"UVHD",
    v30,
    L"DeleteUsrClassLocalSettingRegKeyWithRetry() for user %s return 0x%08x.",
    v29,
    phkResult);
  v31 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v82);
  MountedUvhdMountPoint = RdVhd::Uvhd::CUvhdProfileManager::FindMountedUvhdMountPoint(
                            v31,
                            v32,
                            &v71,
                            (struct CPathString *)&v75);
  if ( MountedUvhdMountPoint < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v14 = 97;
LABEL_42:
    v15 = (unsigned int)MountedUvhdMountPoint;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids, v15);
    goto LABEL_17;
  }
  if ( v71 )
  {
    Type = -1;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v33 = CBaseStringT<unsigned short>::PContents(&v75);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids, v33);
    }
    v34 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v75);
    PIIHandler::Set((PIIHandler *)&v74, v34);
    v3 = v74;
    v35 = &qword_180063A68;
    if ( v74 )
      v35 = (const unsigned __int16 *)v74;
    _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"Found UVHD volume mount point at '%s'", v35);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this) )
    {
      v36 = CBaseStringT<unsigned short>::PContents(&v75);
      if ( v37(v38, v36, &Type) < 0 )
      {
        v39 = CBaseStringT<unsigned short>::PContents(&v75);
        _TraceNrmRdvVmEx(
          L"UVHD",
          v40,
          L"Failed to obtain UVHD disk number for mount point: %s. Ignoring the error.",
          v39);
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = CBaseStringT<unsigned short>::PContents(&v75);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            (unsigned int)&WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids,
            v41,
            v42);
        }
      }
    }
    v43 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v75);
    v45 = RdVhd::Uvhd::CUvhdProfileManager::UnmountUserVhd(this, v43, v44);
    MountedUvhdMountPoint = v45;
    if ( v45 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v14 = 100;
      goto LABEL_66;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this) )
    {
      v46 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents((char *)this + 72);
      v48 = RdVhd::Uvhd::CUvhdProfileManager::DetachUserVhd(this, v46, v47);
      MountedUvhdMountPoint = v48;
      if ( v95 )
      {
        if ( v48 < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_17;
          }
          v14 = 102;
          goto LABEL_81;
        }
      }
      else if ( v48 < 0 )
      {
        v49 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
        _TraceNrmRdvVmEx(
          L"UVHD",
          MountedUvhdMountPoint,
          L"Could not detach UVHD disk on Logon. Possibly recovering from hard-reboot. Ignoring. SID: %s",
          v49);
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v50 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            (unsigned int)&WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids,
            v50,
            MountedUvhdMountPoint);
        }
        MountedUvhdMountPoint = 0;
      }
    }
    v71 = 1;
  }
  else
  {
    v90 = 128;
    v88 = &CPathString::`vftable';
    v92 = 0;
    v91 = 0;
    v93 = 0x8000000;
    v89 = 0;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids);
    }
    v51 = **(_QWORD **)cbData;
    CBaseStringT<unsigned short>::PContents((char *)this + 72);
    v52 = CBaseStringT<unsigned short>::PContents(&v82);
    MountedUvhdMountPoint = v54(v51, v52, v53, &v88);
    v55 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"BackupUserProfile() FAILED; User SID: %s", v55);
    if ( MountedUvhdMountPoint < 0 )
    {
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          &WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids,
          (unsigned int)MountedUvhdMountPoint);
      }
      CPathString::~CPathString((CPathString *)&v88);
      goto LABEL_17;
    }
    v71 = 0;
    if ( !MountedUvhdMountPoint )
    {
      v56 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v88);
      PIIHandler::Set((PIIHandler *)&v74, v56);
      v3 = v74;
      v57 = &qword_180063A68;
      if ( v74 )
        v57 = (const unsigned __int16 *)v74;
      _TraceNrmRdvVmEx(L"UVHD", 0, L"Local User Profile backed up to \"%s\"", v57);
    }
    CPathString::~CPathString((CPathString *)&v88);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 80LL))(*(_QWORD *)this) == 1
    || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this) == 1 )
  {
    goto LABEL_101;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 40LL))(*(_QWORD *)this) == -1 )
  {
    Type = 0;
    v62 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v82);
    MountedUvhdMountPoint = RdVhd::Uvhd::CUvhdProfileManager::IsSymLinkProfile(v63, v62, (int *)&Type);
    v64 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"bSymLinkProfile() FAILED; User SID: %s", v64);
    if ( MountedUvhdMountPoint >= 0 )
    {
      if ( Type != 1 )
        goto LABEL_101;
      v65 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
      _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"SymLink profile for user %s, don't delete profile", v65);
LABEL_113:
      v66 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
      _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"Keep profile for user %s", v66);
      goto LABEL_120;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v14 = 105;
LABEL_81:
    v15 = (unsigned int)MountedUvhdMountPoint;
    goto LABEL_16;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 40LL))(*(_QWORD *)this) == 2 )
    goto LABEL_113;
LABEL_101:
  v58 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
  _TraceNrmRdvVmEx(L"UVHD", MountedUvhdMountPoint, L"Delete profile for user %s", v58);
  v59 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
  v45 = v60(v61, v59);
  MountedUvhdMountPoint = v45;
  if ( v45 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v14 = 106;
LABEL_66:
    v15 = (unsigned int)v45;
    goto LABEL_16;
  }
  if ( v45 == 1 )
  {
    v67 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
    _TraceNrmRdvVmEx(L"UVHD", 1, L"Local user profile exepected to exist, but does not; SID: %s", v67);
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v68 = CBaseStringT<unsigned short>::PContents((char *)this + 72);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        (unsigned int)&WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids,
        v68,
        1);
    }
    MountedUvhdMountPoint = 1;
  }
LABEL_120:
  CPathString::~CPathString((CPathString *)&v75);
  if ( !v71 )
LABEL_121:
    MountedUvhdMountPoint = 1;
LABEL_122:
  GetTickCount();
  operator delete(v3);
  CPathString::~CPathString((CPathString *)&v82);
  return (unsigned int)MountedUvhdMountPoint;
}

```

## disassembly

```asm
0x180045944  mov     [rsp-8+arg_10], r8
0x180045949  mov     [rsp-8+arg_8], edx
0x18004594d  push    rbp
0x18004594e  push    rbx
0x18004594f  push    rsi
0x180045950  push    rdi
0x180045951  push    r12
0x180045953  push    r13
0x180045955  push    r14
0x180045957  push    r15
0x180045959  lea     rbp, [rsp-1Fh]
0x18004595e  sub     rsp, 0D8h
0x180045965  xor     edi, edi
0x180045967  mov     [rbp+57h+var_84], 80h
0x18004596f  mov     ebx, edi
0x180045971  mov     [rbp+57h+var_78], rdi
0x180045975  mov     r14d, 8000000h
0x18004597b  mov     [rbp+57h+var_C8], rbx
0x18004597f  lea     r15, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180045986  mov     [rbp+57h+var_7C], edi
0x180045989  mov     r13, rcx
0x18004598c  mov     [rbp+57h+var_70], r14d
0x180045990  mov     [rbp+57h+var_88], edi
0x180045993  mov     [rbp+57h+var_90], r15
0x180045997  call    cs:__imp_GetTickCount
0x18004599d  mov     rcx, [r13+0]
0x1800459a1  mov     rax, [rcx]
0x1800459a4  mov     rax, [rax+8]
0x1800459a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459ad  test    eax, eax
0x1800459af  jz      loc_1800462C3
0x1800459b5  lea     rax, [rbp+57h+hKey]
0x1800459b9  mov     [rbp+57h+var_A0], r14d
0x1800459bd  mov     r9d, 20019h; samDesired
0x1800459c3  mov     [rsp+110h+phkResult], rax; phkResult
0x1800459c8  xor     r8d, r8d; ulOptions
0x1800459cb  mov     [rbp+57h+arg_0], edi
0x1800459ce  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800459d5  mov     [rsp+110h+var_E0], edi
0x1800459d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800459e0  mov     [rbp+57h+var_B4], 80h
0x1800459e8  mov     [rbp+57h+var_A8], rdi
0x1800459ec  mov     r14d, 7D0h
0x1800459f2  mov     [rbp+57h+var_AC], edi
0x1800459f5  mov     esi, edi
0x1800459f7  mov     [rbp+57h+var_B8], edi
0x1800459fa  mov     [rbp+57h+var_C0], r15
0x1800459fe  mov     [rbp+57h+hKey], rdi
0x180045a02  call    cs:__imp_RegOpenKeyExW
0x180045a08  test    eax, eax
0x180045a0a  jnz     short loc_180045A61
0x180045a0c  mov     rcx, [rbp+57h+hKey]; hKey
0x180045a10  lea     rax, [rsp+110h+cbData]
0x180045a15  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180045a1a  lea     r9, [rbp+57h+Type]; lpType
0x180045a1e  lea     rax, [rbp+57h+Data]
0x180045a22  mov     dword ptr [rbp+57h+Data], edi
0x180045a25  xor     r8d, r8d; lpReserved
0x180045a28  mov     [rsp+110h+phkResult], rax; lpData
0x180045a2d  lea     rdx, aRdupdprofileun; "RDUPDProfileUnloadWaitTime"
0x180045a34  mov     [rsp+110h+cbData], 4
0x180045a3c  mov     [rbp+57h+Type], edi
0x180045a3f  call    cs:__imp_RegQueryValueExW
0x180045a45  test    eax, eax
0x180045a47  jnz     short loc_180045A57
0x180045a49  cmp     [rbp+57h+Type], 4
0x180045a4d  jnz     short loc_180045A57
0x180045a4f  imul    r14d, dword ptr [rbp+57h+Data], 3E8h
0x180045a57  mov     rcx, [rbp+57h+hKey]; hKey
0x180045a5b  call    cs:__imp_RegCloseKey
0x180045a61  lea     rdi, [r13+10h]
0x180045a65  mov     qword ptr [rsp+110h+cbData], rdi
0x180045a6a  lea     r15, [r13+48h]
0x180045a6e  mov     r12, rdi
0x180045a71  cmp     esi, r14d
0x180045a74  ja      loc_180045B07
0x180045a7a  lea     r12, [r13+10h]
0x180045a7e  mov     rcx, r15
0x180045a81  mov     r11, [r12]
0x180045a85  mov     rax, [r11]
0x180045a88  mov     r10, [rax+40h]
0x180045a8c  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045a91  mov     rdx, rax
0x180045a94  lea     r8, [rbp+57h+arg_0]
0x180045a98  mov     rax, r10
0x180045a9b  mov     rcx, r11
0x180045a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aa3  mov     edi, eax
0x180045aa5  test    eax, eax
0x180045aa7  js      short loc_180045AC2
0x180045aa9  cmp     [rbp+57h+arg_0], ebx
0x180045aac  jz      loc_180045B76
0x180045ab2  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180045ab7  call    cs:__imp_Sleep
0x180045abd  add     esi, 64h ; 'd'
0x180045ac0  jmp     short loc_180045A71
0x180045ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ac9  lea     r14, WPP_GLOBAL_Control
0x180045ad0  cmp     rcx, r14
0x180045ad3  jz      short loc_180045AF9
0x180045ad5  test    byte ptr [rcx+1Ch], 4
0x180045ad9  jz      short loc_180045AF9
0x180045adb  cmp     byte ptr [rcx+19h], 2
0x180045adf  jb      short loc_180045AF9
0x180045ae1  mov     edx, 5Ch ; '\'
0x180045ae6  mov     r9d, eax
0x180045ae9  lea     r8, WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids
0x180045af0  mov     rcx, [rcx+10h]
0x180045af4  call    WPP_SF_d
0x180045af9  lea     rcx, [rbp+57h+var_C0]; this
0x180045afd  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180045b02  jmp     loc_1800462C8
0x180045b07  cmp     [rbp+57h+arg_0], ebx
0x180045b0a  jz      short loc_180045B76
0x180045b0c  mov     rcx, r15
0x180045b0f  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045b14  mov     edi, 0D05D00AAh
0x180045b19  lea     r8, aDisconnectprof; "DisconnectProfile(): Profile is in use!"...
0x180045b20  mov     edx, edi; int
0x180045b22  lea     rcx, aUvhd; "UVHD"
0x180045b29  mov     r9, rax
0x180045b2c  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180045b31  mov     rax, cs:WPP_GLOBAL_Control
0x180045b38  lea     r14, WPP_GLOBAL_Control
0x180045b3f  cmp     rax, r14
0x180045b42  jz      short loc_180045AF9
0x180045b44  test    byte ptr [rax+1Ch], 4
0x180045b48  jz      short loc_180045AF9
0x180045b4a  cmp     byte ptr [rax+19h], 2
0x180045b4e  jb      short loc_180045AF9
0x180045b50  mov     rcx, r15
0x180045b53  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b5f  mov     r9d, esi
0x180045b62  mov     dword ptr [rsp+110h+lpcbData], edi
0x180045b66  mov     [rsp+110h+phkResult], rax
0x180045b6b  mov     rcx, [rcx+10h]
0x180045b6f  call    WPP_SF_LSd
0x180045b74  jmp     short loc_180045AF9
0x180045b76  mov     rax, cs:WPP_GLOBAL_Control
0x180045b7d  lea     r14, WPP_GLOBAL_Control
0x180045b84  cmp     rax, r14
0x180045b87  jz      short loc_180045BC5
0x180045b89  test    byte ptr [rax+1Ch], 4
0x180045b8d  jz      short loc_180045BBB
0x180045b8f  cmp     byte ptr [rax+19h], 4
0x180045b93  jb      short loc_180045BC5
0x180045b95  mov     rcx, r15
0x180045b98  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ba4  mov     r9d, esi
0x180045ba7  mov     [rsp+110h+phkResult], rax
0x180045bac  mov     rcx, [rcx+10h]
0x180045bb0  call    WPP_SF_LS
0x180045bb5  lea     rdi, [r13+10h]
0x180045bb9  jmp     short loc_180045BCE
0x180045bbb  mov     rdi, r12
0x180045bbe  mov     qword ptr [rsp+110h+cbData], r12
0x180045bc3  jmp     short loc_180045BCE
0x180045bc5  lea     rdi, [r13+10h]
0x180045bc9  mov     qword ptr [rsp+110h+cbData], rdi
0x180045bce  mov     r10, [rdi]
0x180045bd1  xor     esi, esi
0x180045bd3  mov     rax, [rbp+57h+arg_10]
0x180045bd7  mov     r11, [r10]
0x180045bda  test    rax, rax
0x180045bdd  jz      short loc_180045BF4
0x180045bdf  mov     rdx, rax
0x180045be2  lea     r8, [rbp+57h+var_90]
0x180045be6  mov     rax, [r11+18h]
0x180045bea  mov     rcx, r10
0x180045bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bf2  jmp     short loc_180045C15
0x180045bf4  mov     rcx, r15
0x180045bf7  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045bfc  mov     rdx, rax
0x180045bff  lea     r9, [rbp+57h+var_90]
0x180045c03  mov     rax, [r11+10h]
0x180045c07  mov     r8d, 1
0x180045c0d  mov     rcx, r10
0x180045c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c15  mov     edi, eax
0x180045c17  cmp     di, 2
0x180045c1b  jnz     short loc_180045C5E
0x180045c1d  mov     edi, 1
0x180045c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c29  cmp     rcx, r14
0x180045c2c  jz      loc_180045AF9
0x180045c32  test    byte ptr [rcx+1Ch], 4
0x180045c36  jz      loc_180045AF9
0x180045c3c  cmp     byte ptr [rcx+19h], 4
0x180045c40  jb      loc_180045AF9
0x180045c46  mov     rcx, [rcx+10h]
0x180045c4a  lea     edx, [rdi+5Eh]
0x180045c4d  lea     r8, WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids
0x180045c54  call    WPP_SF_
0x180045c59  jmp     loc_180045AF9
0x180045c5e  test    edi, edi
0x180045c60  jns     short loc_180045C93
0x180045c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180045c69  cmp     rcx, r14
0x180045c6c  jz      loc_180045AF9
0x180045c72  test    byte ptr [rcx+1Ch], 4
0x180045c76  jz      loc_180045AF9
0x180045c7c  cmp     byte ptr [rcx+19h], 2
0x180045c80  jb      loc_180045AF9
0x180045c86  mov     edx, 60h ; '`'
0x180045c8b  mov     r9d, edi
0x180045c8e  jmp     loc_180045AE9
0x180045c93  lea     rcx, [rbp+57h+var_90]
0x180045c97  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045c9c  mov     rdx, rax; unsigned __int16 *
0x180045c9f  mov     rcx, r13; this
0x180045ca2  call    ?DeleteUsrClassLocalSettingRegKeyWithRetry@CUvhdProfileManager@Uvhd@RdVhd@@IEAAJPEBG@Z; RdVhd::Uvhd::CUvhdProfileManager::DeleteUsrClassLocalSettingRegKeyWithRetry(ushort const *)
0x180045ca7  mov     rcx, r15
0x180045caa  mov     r10d, eax
0x180045cad  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045cb2  lea     r12, aUvhd; "UVHD"
0x180045cb9  mov     dword ptr [rsp+110h+phkResult], r10d
0x180045cbe  mov     rcx, r12; unsigned __int16 *
0x180045cc1  lea     r8, aDeleteusrclass; "DeleteUsrClassLocalSettingRegKeyWithRet"...
0x180045cc8  mov     r9, rax
0x180045ccb  mov     edx, r10d; int
0x180045cce  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180045cd3  mov     r10, [r13+8]
0x180045cd7  lea     rcx, [rbp+57h+var_90]
0x180045cdb  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045ce0  lea     r9, [rbp+57h+var_C0]; struct CPathString *
0x180045ce4  mov     rdx, r10; struct RdVhd::Uvhd::IDirectoryHelper *
0x180045ce7  lea     r8, [rsp+110h+var_E0]; int *
0x180045cec  mov     rcx, rax; unsigned __int16 *
0x180045cef  call    ?FindMountedUvhdMountPoint@CUvhdProfileManager@Uvhd@RdVhd@@KAJPEBGPEAVIDirectoryHelper@23@PEAHPEAVCPathString@@@Z; RdVhd::Uvhd::CUvhdProfileManager::FindMountedUvhdMountPoint(ushort const *,RdVhd::Uvhd::IDirectoryHelper *,int *,CPathString *)
0x180045cf4  mov     edi, eax
0x180045cf6  test    eax, eax
0x180045cf8  jns     short loc_180045D28
0x180045cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d01  cmp     rcx, r14
0x180045d04  jz      loc_180045AF9
0x180045d0a  test    byte ptr [rcx+1Ch], 4
0x180045d0e  jz      loc_180045AF9
0x180045d14  cmp     byte ptr [rcx+19h], 2
0x180045d18  jb      loc_180045AF9
0x180045d1e  mov     edx, 61h ; 'a'
0x180045d23  jmp     loc_180045C8B
0x180045d28  cmp     [rsp+110h+var_E0], esi
0x180045d2c  jz      loc_180045F91
0x180045d32  mov     [rbp+57h+Type], 0FFFFFFFFh
0x180045d39  mov     rax, cs:WPP_GLOBAL_Control
0x180045d40  lea     rsi, WPP_51d6cb8edda1332360d49ca8c94b4b20_Traceguids
0x180045d47  cmp     rax, r14
0x180045d4a  jz      short loc_180045D7C
0x180045d4c  test    byte ptr [rax+1Ch], 4
0x180045d50  jz      short loc_180045D7C
0x180045d52  cmp     byte ptr [rax+19h], 4
0x180045d56  jb      short loc_180045D7C
0x180045d58  lea     rcx, [rbp+57h+var_C0]
0x180045d5c  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d68  mov     edx, 62h ; 'b'
0x180045d6d  mov     r9, rax
0x180045d70  mov     r8, rsi
0x180045d73  mov     rcx, [rcx+10h]
0x180045d77  call    WPP_SF_S
0x180045d7c  lea     rcx, [rbp+57h+var_C0]
0x180045d80  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045d85  mov     rdx, rax; unsigned __int16 *
0x180045d88  lea     rcx, [rbp+57h+var_C8]; this
0x180045d8c  call    ?Set@PIIHandler@@QEAAJPEBG@Z; PIIHandler::Set(ushort const *)
0x180045d91  mov     rbx, [rbp+57h+var_C8]
0x180045d95  lea     r9, qword_180063A68
0x180045d9c  test    rbx, rbx
0x180045d9f  lea     r8, aFoundUvhdVolum; "Found UVHD volume mount point at '%s'"
0x180045da6  mov     edx, edi; int
0x180045da8  mov     rcx, r12; unsigned __int16 *
0x180045dab  cmovnz  r9, rbx
0x180045daf  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180045db4  mov     rcx, [r13+0]
0x180045db8  mov     rax, [rcx]
0x180045dbb  mov     rax, [rax+20h]
0x180045dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dc4  test    eax, eax
0x180045dc6  jz      loc_180045E58
0x180045dcc  mov     r11, [r13+18h]
0x180045dd0  lea     rcx, [rbp+57h+var_C0]
0x180045dd4  mov     rax, [r11]
0x180045dd7  mov     r10, [rax+40h]
0x180045ddb  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045de0  mov     rdx, rax
0x180045de3  lea     r8, [rbp+57h+Type]
0x180045de7  mov     rax, r10
0x180045dea  mov     rcx, r11
0x180045ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045df2  mov     r10d, eax
0x180045df5  test    eax, eax
0x180045df7  jns     short loc_180045E58
0x180045df9  lea     rcx, [rbp+57h+var_C0]
0x180045dfd  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180045e02  mov     r9, rax
0x180045e05  lea     r8, aFailedToObtain; "Failed to obtain UVHD disk number for m"...
0x180045e0c  mov     edx, r10d; int
  ... truncated ...
```
