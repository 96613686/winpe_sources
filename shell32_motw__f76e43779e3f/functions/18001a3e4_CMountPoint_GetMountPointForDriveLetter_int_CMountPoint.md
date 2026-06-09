# CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)

- ea: `0x18001a3e4`
- end: `0x18001a719`
- name: `?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z`
- size: `821`
- prototype: `__int64 __fastcall(int, struct CMountPoint **)`
- caller_count: `3`
- callee_count: `21`
- tags: `reparse_path, loader_planting`

## callers

- `0x180019a0c`
- `0x18001a064`
- `0x18001a96c`

## callees

- `0x18001a2bc`
- `0x18001a3e4`
- `0x18001a720`
- `0x18001aa98`
- `0x18009a63c`
- `0x18009a6d8`
- `0x18009a700`
- `0x18009a838`
- `0x18009ac88`
- `0x18012f0b8`
- `0x180154d14`
- `0x18017ec14`
- `0x1801928f0`
- `0x1801e80a4`
- `0x1801eeadc`
- `0x180249490`
- `0x18057e5f4`
- `0x180580f84`
- `0x18058133c`
- `0x18058158c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001a504`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001a504`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x18001a47a`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x18001a47a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a6a9`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18001a4f5`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18001a5bc`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18001a4f5`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18001a5bc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a421`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a440`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a558`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a571`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a593`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a605`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a65a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a66f`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a683`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a699`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a6c7`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a421`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a440`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a558`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a571`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a593`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a605`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a65a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a66f`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a683`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a699`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18001a6c7`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x18001a637`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x18001a637`

## pseudocode

```c
__int64 __fastcall CMountPoint::_GetMountPointForDriveLetter(int a1, struct CMountPoint **a2)
{
  __int64 v2; // rsi
  __int64 v4; // rax
  struct CMountPoint *v5; // rdi
  struct CMountPoint **v6; // rdx
  DWORD v7; // eax
  __int64 result; // rax
  const WCHAR *v9; // rax
  UINT DriveTypeW; // eax
  __int64 v11; // rax
  struct CMtPtLocal *Remote; // rax
  __int64 v13; // rax
  struct CDriveLetterData *DriveLetterData; // rax
  CDriveLetterCache *v15; // rcx
  const unsigned __int16 *v16; // rax
  struct CVolume *VolumeByMtPt; // rax
  CVolume *v18; // r14
  int MtPtLocalWithVolume; // ebx
  CMountPoint *v20; // rcx
  __int64 v21; // rax
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  char *v26; // rbx
  CVolume *v27; // [rsp+20h] [rbp-20h] BYREF
  WCHAR pszRoot[4]; // [rsp+28h] [rbp-18h] BYREF

  v2 = a1;
  *a2 = 0;
  if ( (unsigned int)CMountPoint::_IsNetDriveLazyLoadNetDLLs(a1) )
  {
    if ( !*(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1104) )
      CMountPoint::_InitNetDrives();
    v11 = Global_WindowsStorage_Untyped_MountPoint();
    Remote = CDriveLetterCache::GetRemote((CDriveLetterCache *)(v11 + 264), v2);
    goto LABEL_23;
  }
  if ( !*(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1108) )
  {
    if ( (unsigned int)IsDesktopExplorerProcess() )
    {
      CMountPoint::_InitLocalDrives();
    }
    else
    {
      CMountPoint::_InitLocalDrive(v2);
      v22 = 0;
      v23 = Global_WindowsStorage_Untyped_MountPoint();
      CCritSecDelayInitBase::Enter((PVOID)(v23 + 56));
      if ( !*(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1112) )
      {
        v22 = 1;
        *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1112) = 1;
      }
      v24 = Global_WindowsStorage_Untyped_MountPoint();
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 56));
      if ( v22 )
        CMountPoint::_InitLocalDrivesAsync();
    }
  }
  v4 = Global_WindowsStorage_Untyped_MountPoint();
  v5 = 0;
  if ( (unsigned int)v2 <= 0x19 )
  {
    v6 = (struct CMountPoint **)(v4 + 32 * v2 + 264);
    if ( v6 )
    {
      if ( *v6 )
      {
        _InterlockedAdd((volatile signed __int32 *)*v6 + 12, 1u);
        v5 = *v6;
      }
    }
  }
  *(_QWORD *)pszRoot = v5;
  v7 = (1 << v2) & GetLogicalDrives();
  if ( !v5 )
  {
    if ( !v7 )
      goto LABEL_12;
    v9 = PathBuildRootW(pszRoot, v2);
    DriveTypeW = GetDriveTypeW(v9);
    if ( DriveTypeW - 2 > 1 && DriveTypeW - 5 > 1 )
      goto LABEL_12;
    v27 = 0;
    if ( (int)CMtPtLocal::_CreateVolumeFromReg(pszRoot, &v27) < 0 )
    {
      CMtPtLocal::_CreateMtPtLocal(pszRoot);
    }
    else
    {
      CMtPtLocal::_CreateMtPtLocalWithVolume(pszRoot, v27);
      CVolume::Release(v27);
    }
    goto LABEL_29;
  }
  if ( !v7 )
  {
    v25 = Global_WindowsStorage_Untyped_MountPoint();
    CDriveLetterCache::SetRemote((CDriveLetterCache *)(v25 + 264), v2, 0);
    SafeRelease<CMtPtRemote>(pszRoot);
    v5 = *(struct CMountPoint **)pszRoot;
  }
  if ( v5 && (*(unsigned int (__fastcall **)(struct CMountPoint *))(*(_QWORD *)v5 + 608LL))(v5) )
  {
    v13 = Global_WindowsStorage_Untyped_MountPoint();
    DriveLetterData = CDriveLetterCache::GetDriveLetterData((CDriveLetterCache *)(v13 + 264), v2);
    if ( DriveLetterData )
    {
      v26 = (char *)DriveLetterData + 8;
      CDriveLetterCache::RemovePathLookupEntry(v15, *((struct CMountPoint **)DriveLetterData + 1));
      SafeRelease<CMtPtRemote>(v26);
    }
    v16 = PathBuildRootW(pszRoot, v2);
    VolumeByMtPt = CMtPtLocal::_GetVolumeByMtPt(v16);
    v18 = VolumeByMtPt;
    if ( VolumeByMtPt )
    {
      MtPtLocalWithVolume = CMtPtLocal::_CreateMtPtLocalWithVolume(pszRoot, VolumeByMtPt);
      CVolume::Release(v18);
    }
    else
    {
      MtPtLocalWithVolume = CMtPtLocal::_CreateMtPtLocal(pszRoot);
    }
    v20 = v5;
    v5 = 0;
    CMountPoint::Release(v20);
    if ( MtPtLocalWithVolume >= 0 )
    {
LABEL_29:
      v21 = Global_WindowsStorage_Untyped_MountPoint();
      Remote = CDriveLetterCache::GetLocal((CDriveLetterCache *)(v21 + 264), v2);
LABEL_23:
      v5 = Remote;
    }
  }
LABEL_12:
  result = 2147500037LL;
  if ( v5 )
  {
    *a2 = v5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a3e4  mov     [rsp-28h+arg_10], rbx
0x18001a3e9  push    rbp
0x18001a3ea  push    rsi
0x18001a3eb  push    rdi
0x18001a3ec  push    r14
0x18001a3ee  push    r15
0x18001a3f0  mov     rbp, rsp
0x18001a3f3  sub     rsp, 40h
0x18001a3f7  mov     rax, cs:__security_cookie
0x18001a3fe  xor     rax, rsp
0x18001a401  mov     [rbp+var_10], rax
0x18001a405  movsxd  rsi, ecx
0x18001a408  mov     r15, rdx
0x18001a40b  mov     ecx, esi; int
0x18001a40d  mov     qword ptr [rdx], 0
0x18001a414  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x18001a419  test    eax, eax
0x18001a41b  jnz     loc_18001A558
0x18001a421  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a428  nop     dword ptr [rax+rax+00h]
0x18001a42d  mov     r14d, 1
0x18001a433  cmp     dword ptr [rax+454h], 0
0x18001a43a  jz      loc_18001A637
0x18001a440  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a447  nop     dword ptr [rax+rax+00h]
0x18001a44c  xor     edi, edi
0x18001a44e  cmp     esi, 19h
0x18001a451  ja      short loc_18001A476
0x18001a453  mov     rdx, rsi
0x18001a456  shl     rdx, 5
0x18001a45a  add     rdx, 108h
0x18001a461  add     rdx, rax
0x18001a464  jz      short loc_18001A476
0x18001a466  mov     rax, [rdx]
0x18001a469  test    rax, rax
0x18001a46c  jz      short loc_18001A476
0x18001a46e  lock add [rax+30h], r14d
0x18001a473  mov     rdi, [rdx]
0x18001a476  mov     qword ptr [rbp+pszRoot], rdi
0x18001a47a  call    cs:__imp_GetLogicalDrives
0x18001a481  nop     dword ptr [rax+rax+00h]
0x18001a486  mov     ecx, esi
0x18001a488  mov     edx, r14d
0x18001a48b  shl     edx, cl
0x18001a48d  and     eax, edx
0x18001a48f  test    rdi, rdi
0x18001a492  jz      short loc_18001A4EB
0x18001a494  test    eax, eax
0x18001a496  jz      loc_18001A6C7
0x18001a49c  test    rdi, rdi
0x18001a49f  jz      short loc_18001A4BB
0x18001a4a1  mov     rax, [rdi]
0x18001a4a4  mov     rcx, rdi
0x18001a4a7  mov     rax, [rax+260h]
0x18001a4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4b3  test    eax, eax
0x18001a4b5  jnz     loc_18001A593
0x18001a4bb  mov     eax, 80004005h
0x18001a4c0  test    rdi, rdi
0x18001a4c3  jz      short loc_18001A4CA
0x18001a4c5  mov     [r15], rdi
0x18001a4c8  xor     eax, eax
0x18001a4ca  mov     rcx, [rbp+var_10]
0x18001a4ce  xor     rcx, rsp; StackCookie
0x18001a4d1  call    __security_check_cookie
0x18001a4d6  mov     rbx, [rsp+40h+arg_10]
0x18001a4de  add     rsp, 40h
0x18001a4e2  pop     r15
0x18001a4e4  pop     r14
0x18001a4e6  pop     rdi
0x18001a4e7  pop     rsi
0x18001a4e8  pop     rbp
0x18001a4e9  retn
0x18001a4eb  test    eax, eax
0x18001a4ed  jz      short loc_18001A4BB
0x18001a4ef  mov     edx, esi; iDrive
0x18001a4f1  lea     rcx, [rbp+pszRoot]; pszRoot
0x18001a4f5  call    cs:__imp_PathBuildRootW
0x18001a4fc  nop     dword ptr [rax+rax+00h]
0x18001a501  mov     rcx, rax; lpRootPathName
0x18001a504  call    cs:__imp_GetDriveTypeW
0x18001a50b  nop     dword ptr [rax+rax+00h]
0x18001a510  lea     ecx, [rax-2]
0x18001a513  cmp     ecx, r14d
0x18001a516  jbe     short loc_18001A520
0x18001a518  add     eax, 0FFFFFFFBh
0x18001a51b  cmp     eax, r14d
0x18001a51e  ja      short loc_18001A4BB
0x18001a520  lea     rdx, [rbp+var_20]; struct CVolume **
0x18001a524  mov     [rbp+var_20], 0
0x18001a52c  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x18001a530  call    ?_CreateVolumeFromReg@CMtPtLocal@@CAJPEBGPEAPEAVCVolume@@@Z; CMtPtLocal::_CreateVolumeFromReg(ushort const *,CVolume * *)
0x18001a535  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x18001a539  test    eax, eax
0x18001a53b  js      loc_18001A70F
0x18001a541  mov     rdx, [rbp+var_20]; struct CVolume *
0x18001a545  call    ?_CreateMtPtLocalWithVolume@CMtPtLocal@@CAJPEBGPEAVCVolume@@@Z; CMtPtLocal::_CreateMtPtLocalWithVolume(ushort const *,CVolume *)
0x18001a54a  mov     rcx, [rbp+var_20]; this
0x18001a54e  call    ?Release@CVolume@@QEAAKXZ; CVolume::Release(void)
0x18001a553  jmp     loc_18001A605
0x18001a558  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a55f  nop     dword ptr [rax+rax+00h]
0x18001a564  cmp     dword ptr [rax+450h], 0
0x18001a56b  jz      loc_18001A62D
0x18001a571  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a578  nop     dword ptr [rax+rax+00h]
0x18001a57d  mov     edx, esi; int
0x18001a57f  lea     rcx, [rax+108h]; this
0x18001a586  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x18001a58b  mov     rdi, rax
0x18001a58e  jmp     loc_18001A4BB
0x18001a593  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a59a  nop     dword ptr [rax+rax+00h]
0x18001a59f  mov     edx, esi; int
0x18001a5a1  lea     rcx, [rax+108h]; this
0x18001a5a8  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x18001a5ad  test    rax, rax
0x18001a5b0  jnz     loc_18001A6F6
0x18001a5b6  mov     edx, esi; iDrive
0x18001a5b8  lea     rcx, [rbp+pszRoot]; pszRoot
0x18001a5bc  call    cs:__imp_PathBuildRootW
0x18001a5c3  nop     dword ptr [rax+rax+00h]
0x18001a5c8  mov     rcx, rax; unsigned __int16 *
0x18001a5cb  call    ?_GetVolumeByMtPt@CMtPtLocal@@CAPEAVCVolume@@PEBG@Z; CMtPtLocal::_GetVolumeByMtPt(ushort const *)
0x18001a5d0  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x18001a5d4  mov     r14, rax
0x18001a5d7  test    rax, rax
0x18001a5da  jz      short loc_18001A624
0x18001a5dc  mov     rdx, rax; struct CVolume *
0x18001a5df  call    ?_CreateMtPtLocalWithVolume@CMtPtLocal@@CAJPEBGPEAVCVolume@@@Z; CMtPtLocal::_CreateMtPtLocalWithVolume(ushort const *,CVolume *)
0x18001a5e4  mov     rcx, r14; this
0x18001a5e7  mov     ebx, eax
0x18001a5e9  call    ?Release@CVolume@@QEAAKXZ; CVolume::Release(void)
0x18001a5ee  mov     rcx, rdi; this
0x18001a5f1  xor     edi, edi
0x18001a5f3  test    rcx, rcx
0x18001a5f6  jz      short loc_18001A5FD
0x18001a5f8  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18001a5fd  test    ebx, ebx
0x18001a5ff  js      loc_18001A4BB
0x18001a605  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a60c  nop     dword ptr [rax+rax+00h]
0x18001a611  mov     edx, esi; int
0x18001a613  lea     rcx, [rax+108h]; this
0x18001a61a  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x18001a61f  jmp     loc_18001A58B
0x18001a624  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x18001a629  mov     ebx, eax
0x18001a62b  jmp     short loc_18001A5EE
0x18001a62d  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x18001a632  jmp     loc_18001A571
0x18001a637  call    cs:__imp_IsDesktopExplorerProcess
0x18001a63e  nop     dword ptr [rax+rax+00h]
0x18001a643  test    eax, eax
0x18001a645  jz      short loc_18001A651
0x18001a647  call    ?_InitLocalDrives@CMountPoint@@CAJXZ; CMountPoint::_InitLocalDrives(void)
0x18001a64c  jmp     loc_18001A440
0x18001a651  mov     ecx, esi; int
0x18001a653  call    ?_InitLocalDrive@CMountPoint@@CAJH@Z; CMountPoint::_InitLocalDrive(int)
0x18001a658  xor     ebx, ebx
0x18001a65a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a661  nop     dword ptr [rax+rax+00h]
0x18001a666  lea     rcx, [rax+38h]; Parameter
0x18001a66a  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x18001a66f  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a676  nop     dword ptr [rax+rax+00h]
0x18001a67b  cmp     [rax+458h], ebx
0x18001a681  jnz     short loc_18001A699
0x18001a683  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a68a  nop     dword ptr [rax+rax+00h]
0x18001a68f  mov     ebx, r14d
0x18001a692  mov     [rax+458h], r14d
0x18001a699  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a6a0  nop     dword ptr [rax+rax+00h]
0x18001a6a5  lea     rcx, [rax+38h]; lpCriticalSection
0x18001a6a9  call    cs:__imp_LeaveCriticalSection
0x18001a6b0  nop     dword ptr [rax+rax+00h]
0x18001a6b5  test    ebx, ebx
0x18001a6b7  jz      loc_18001A440
0x18001a6bd  call    ?_InitLocalDrivesAsync@CMountPoint@@CAJXZ; CMountPoint::_InitLocalDrivesAsync(void)
0x18001a6c2  jmp     loc_18001A440
0x18001a6c7  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18001a6ce  nop     dword ptr [rax+rax+00h]
0x18001a6d3  xor     r8d, r8d; struct CMtPtRemote *
0x18001a6d6  mov     edx, esi; int
0x18001a6d8  lea     rcx, [rax+108h]; this
0x18001a6df  call    ?SetRemote@CDriveLetterCache@@QEAAXHPEAVCMtPtRemote@@@Z; CDriveLetterCache::SetRemote(int,CMtPtRemote *)
0x18001a6e4  lea     rcx, [rbp+pszRoot]
0x18001a6e8  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x18001a6ed  mov     rdi, qword ptr [rbp+pszRoot]
0x18001a6f1  jmp     loc_18001A49C
0x18001a6f6  lea     rbx, [rax+8]
0x18001a6fa  mov     rdx, [rbx]; struct CMountPoint *
0x18001a6fd  call    ?RemovePathLookupEntry@CDriveLetterCache@@QEAAXPEAVCMountPoint@@@Z; CDriveLetterCache::RemovePathLookupEntry(CMountPoint *)
0x18001a702  mov     rcx, rbx
0x18001a705  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x18001a70a  jmp     loc_18001A5B6
0x18001a70f  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x18001a714  jmp     loc_18001A605
```
