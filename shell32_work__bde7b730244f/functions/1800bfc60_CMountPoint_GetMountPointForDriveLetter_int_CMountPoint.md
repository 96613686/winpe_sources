# CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)

- ea: `0x1800bfc60`
- end: `0x1800bff2e`
- name: `?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z`
- size: `718`
- prototype: `__int64 __fastcall(int, struct CMountPoint **)`
- caller_count: `3`
- callee_count: `21`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800bf340`
- `0x1800bf924`
- `0x1800c00a0`

## callees

- `0x1800bee2c`
- `0x1800bfb48`
- `0x1800bfc60`
- `0x1800bff34`
- `0x1800c0204`
- `0x1800c0c44`
- `0x1800c0c5c`
- `0x1800c0d3c`
- `0x1800c0db4`
- `0x1800c0e20`
- `0x1800c0e68`
- `0x1800c0e98`
- `0x180180a3c`
- `0x1801d13c0`
- `0x1801d7910`
- `0x180233280`
- `0x18053f7fc`
- `0x180541e54`
- `0x18054217c`
- `0x180542360`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800bfd67`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800bfd67`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800bfcea`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800bfcea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfeca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bfeca`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800bfd5e`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800bfe07`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800bfd5e`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800bfe07`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfc9d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfcb6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfdb5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfdc8`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfde4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfe4a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfe93`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfea2`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfeb0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfec0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfee2`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfc9d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfcb6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfdb5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfdc8`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfde4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfe4a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfe93`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfea2`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfeb0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfec0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1800bfee2`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1800bfe76`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1800bfe76`

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
0x1800bfc60  mov     [rsp-28h+arg_10], rbx
0x1800bfc65  push    rbp
0x1800bfc66  push    rsi
0x1800bfc67  push    rdi
0x1800bfc68  push    r14
0x1800bfc6a  push    r15
0x1800bfc6c  mov     rbp, rsp
0x1800bfc6f  sub     rsp, 40h
0x1800bfc73  mov     rax, cs:__security_cookie
0x1800bfc7a  xor     rax, rsp
0x1800bfc7d  mov     [rbp+var_10], rax
0x1800bfc81  movsxd  rsi, ecx
0x1800bfc84  mov     r15, rdx
0x1800bfc87  mov     ecx, esi; int
0x1800bfc89  mov     qword ptr [rdx], 0
0x1800bfc90  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x1800bfc95  test    eax, eax
0x1800bfc97  jnz     loc_1800BFDB5
0x1800bfc9d  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfca3  mov     r14d, 1
0x1800bfca9  cmp     dword ptr [rax+454h], 0
0x1800bfcb0  jz      loc_1800BFE76
0x1800bfcb6  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfcbc  xor     edi, edi
0x1800bfcbe  cmp     esi, 19h
0x1800bfcc1  ja      short loc_1800BFCE6
0x1800bfcc3  mov     rdx, rsi
0x1800bfcc6  shl     rdx, 5
0x1800bfcca  add     rdx, 108h
0x1800bfcd1  add     rdx, rax
0x1800bfcd4  jz      short loc_1800BFCE6
0x1800bfcd6  mov     rax, [rdx]
0x1800bfcd9  test    rax, rax
0x1800bfcdc  jz      short loc_1800BFCE6
0x1800bfcde  lock add [rax+30h], r14d
0x1800bfce3  mov     rdi, [rdx]
0x1800bfce6  mov     qword ptr [rbp+pszRoot], rdi
0x1800bfcea  call    cs:__imp_GetLogicalDrives
0x1800bfcf0  mov     ecx, esi
0x1800bfcf2  mov     edx, r14d
0x1800bfcf5  shl     edx, cl
0x1800bfcf7  and     eax, edx
0x1800bfcf9  test    rdi, rdi
0x1800bfcfc  jz      short loc_1800BFD54
0x1800bfcfe  test    eax, eax
0x1800bfd00  jz      loc_1800BFEE2
0x1800bfd06  test    rdi, rdi
0x1800bfd09  jz      short loc_1800BFD25
0x1800bfd0b  mov     rax, [rdi]
0x1800bfd0e  mov     rcx, rdi
0x1800bfd11  mov     rax, [rax+260h]
0x1800bfd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfd1d  test    eax, eax
0x1800bfd1f  jnz     loc_1800BFDE4
0x1800bfd25  mov     eax, 80004005h
0x1800bfd2a  test    rdi, rdi
0x1800bfd2d  jz      short loc_1800BFD34
0x1800bfd2f  mov     [r15], rdi
0x1800bfd32  xor     eax, eax
0x1800bfd34  mov     rcx, [rbp+var_10]
0x1800bfd38  xor     rcx, rsp; StackCookie
0x1800bfd3b  call    __security_check_cookie
0x1800bfd40  mov     rbx, [rsp+40h+arg_10]
0x1800bfd48  add     rsp, 40h
0x1800bfd4c  pop     r15
0x1800bfd4e  pop     r14
0x1800bfd50  pop     rdi
0x1800bfd51  pop     rsi
0x1800bfd52  pop     rbp
0x1800bfd53  retn
0x1800bfd54  test    eax, eax
0x1800bfd56  jz      short loc_1800BFD25
0x1800bfd58  mov     edx, esi; iDrive
0x1800bfd5a  lea     rcx, [rbp+pszRoot]; pszRoot
0x1800bfd5e  call    cs:__imp_PathBuildRootW
0x1800bfd64  mov     rcx, rax; lpRootPathName
0x1800bfd67  call    cs:__imp_GetDriveTypeW
0x1800bfd6d  lea     ecx, [rax-2]
0x1800bfd70  cmp     ecx, r14d
0x1800bfd73  jbe     short loc_1800BFD7D
0x1800bfd75  add     eax, 0FFFFFFFBh
0x1800bfd78  cmp     eax, r14d
0x1800bfd7b  ja      short loc_1800BFD25
0x1800bfd7d  lea     rdx, [rbp+var_20]; struct CVolume **
0x1800bfd81  mov     [rbp+var_20], 0
0x1800bfd89  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x1800bfd8d  call    ?_CreateVolumeFromReg@CMtPtLocal@@CAJPEBGPEAPEAVCVolume@@@Z; CMtPtLocal::_CreateVolumeFromReg(ushort const *,CVolume * *)
0x1800bfd92  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x1800bfd96  test    eax, eax
0x1800bfd98  js      loc_1800BFF24
0x1800bfd9e  mov     rdx, [rbp+var_20]; struct CVolume *
0x1800bfda2  call    ?_CreateMtPtLocalWithVolume@CMtPtLocal@@CAJPEBGPEAVCVolume@@@Z; CMtPtLocal::_CreateMtPtLocalWithVolume(ushort const *,CVolume *)
0x1800bfda7  mov     rcx, [rbp+var_20]; this
0x1800bfdab  call    ?Release@CVolume@@QEAAKXZ; CVolume::Release(void)
0x1800bfdb0  jmp     loc_1800BFE4A
0x1800bfdb5  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfdbb  cmp     dword ptr [rax+450h], 0
0x1800bfdc2  jz      loc_1800BFE6C
0x1800bfdc8  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfdce  mov     edx, esi; int
0x1800bfdd0  lea     rcx, [rax+108h]; this
0x1800bfdd7  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x1800bfddc  mov     rdi, rax
0x1800bfddf  jmp     loc_1800BFD25
0x1800bfde4  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfdea  mov     edx, esi; int
0x1800bfdec  lea     rcx, [rax+108h]; this
0x1800bfdf3  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x1800bfdf8  test    rax, rax
0x1800bfdfb  jnz     loc_1800BFF0B
0x1800bfe01  mov     edx, esi; iDrive
0x1800bfe03  lea     rcx, [rbp+pszRoot]; pszRoot
0x1800bfe07  call    cs:__imp_PathBuildRootW
0x1800bfe0d  mov     rcx, rax; unsigned __int16 *
0x1800bfe10  call    ?_GetVolumeByMtPt@CMtPtLocal@@CAPEAVCVolume@@PEBG@Z; CMtPtLocal::_GetVolumeByMtPt(ushort const *)
0x1800bfe15  lea     rcx, [rbp+pszRoot]; unsigned __int16 *
0x1800bfe19  mov     r14, rax
0x1800bfe1c  test    rax, rax
0x1800bfe1f  jz      short loc_1800BFE63
0x1800bfe21  mov     rdx, rax; struct CVolume *
0x1800bfe24  call    ?_CreateMtPtLocalWithVolume@CMtPtLocal@@CAJPEBGPEAVCVolume@@@Z; CMtPtLocal::_CreateMtPtLocalWithVolume(ushort const *,CVolume *)
0x1800bfe29  mov     rcx, r14; this
0x1800bfe2c  mov     ebx, eax
0x1800bfe2e  call    ?Release@CVolume@@QEAAKXZ; CVolume::Release(void)
0x1800bfe33  mov     rcx, rdi; this
0x1800bfe36  xor     edi, edi
0x1800bfe38  test    rcx, rcx
0x1800bfe3b  jz      short loc_1800BFE42
0x1800bfe3d  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1800bfe42  test    ebx, ebx
0x1800bfe44  js      loc_1800BFD25
0x1800bfe4a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfe50  mov     edx, esi; int
0x1800bfe52  lea     rcx, [rax+108h]; this
0x1800bfe59  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x1800bfe5e  jmp     loc_1800BFDDC
0x1800bfe63  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x1800bfe68  mov     ebx, eax
0x1800bfe6a  jmp     short loc_1800BFE33
0x1800bfe6c  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x1800bfe71  jmp     loc_1800BFDC8
0x1800bfe76  call    cs:__imp_IsDesktopExplorerProcess
0x1800bfe7c  test    eax, eax
0x1800bfe7e  jz      short loc_1800BFE8A
0x1800bfe80  call    ?_InitLocalDrives@CMountPoint@@CAJXZ; CMountPoint::_InitLocalDrives(void)
0x1800bfe85  jmp     loc_1800BFCB6
0x1800bfe8a  mov     ecx, esi; int
0x1800bfe8c  call    ?_InitLocalDrive@CMountPoint@@CAJH@Z; CMountPoint::_InitLocalDrive(int)
0x1800bfe91  xor     ebx, ebx
0x1800bfe93  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfe99  lea     rcx, [rax+38h]; Parameter
0x1800bfe9d  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800bfea2  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfea8  cmp     [rax+458h], ebx
0x1800bfeae  jnz     short loc_1800BFEC0
0x1800bfeb0  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfeb6  mov     ebx, r14d
0x1800bfeb9  mov     [rax+458h], r14d
0x1800bfec0  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfec6  lea     rcx, [rax+38h]; lpCriticalSection
0x1800bfeca  call    cs:__imp_LeaveCriticalSection
0x1800bfed0  test    ebx, ebx
0x1800bfed2  jz      loc_1800BFCB6
0x1800bfed8  call    ?_InitLocalDrivesAsync@CMountPoint@@CAJXZ; CMountPoint::_InitLocalDrivesAsync(void)
0x1800bfedd  jmp     loc_1800BFCB6
0x1800bfee2  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1800bfee8  xor     r8d, r8d; struct CMtPtRemote *
0x1800bfeeb  mov     edx, esi; int
0x1800bfeed  lea     rcx, [rax+108h]; this
0x1800bfef4  call    ?SetRemote@CDriveLetterCache@@QEAAXHPEAVCMtPtRemote@@@Z; CDriveLetterCache::SetRemote(int,CMtPtRemote *)
0x1800bfef9  lea     rcx, [rbp+pszRoot]
0x1800bfefd  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x1800bff02  mov     rdi, qword ptr [rbp+pszRoot]
0x1800bff06  jmp     loc_1800BFD06
0x1800bff0b  lea     rbx, [rax+8]
0x1800bff0f  mov     rdx, [rbx]; struct CMountPoint *
0x1800bff12  call    ?RemovePathLookupEntry@CDriveLetterCache@@QEAAXPEAVCMountPoint@@@Z; CDriveLetterCache::RemovePathLookupEntry(CMountPoint *)
0x1800bff17  mov     rcx, rbx
0x1800bff1a  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x1800bff1f  jmp     loc_1800BFE01
0x1800bff24  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x1800bff29  jmp     loc_1800BFE4A
```
