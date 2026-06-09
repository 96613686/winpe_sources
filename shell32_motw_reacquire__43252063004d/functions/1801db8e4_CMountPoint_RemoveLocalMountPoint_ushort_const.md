# CMountPoint::_RemoveLocalMountPoint(ushort const *)

- ea: `0x1801db8e4`
- end: `0x1801dba59`
- name: `?_RemoveLocalMountPoint@CMountPoint@@KAJPEBG@Z`
- size: `373`
- prototype: `__int64 __fastcall(LPCWSTR lpString2)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18009ac88`
- `0x180580a70`
- `0x180583854`

## callees

- `0x18001a2bc`
- `0x18001a2fc`
- `0x18001aa98`
- `0x180067938`
- `0x18009a6d8`
- `0x18009a700`
- `0x18009a838`
- `0x1800f0320`
- `0x1801db8e4`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801dba41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801dba41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801db9c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801db9c8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1801db924`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1801db924`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db8f9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db90e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db952`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db967`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db97b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db99e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db9e4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801dba0e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801dba32`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db8f9`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db90e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db952`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db967`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db97b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db99e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801db9e4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801dba0e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1801dba32`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1801db9fe`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1801db9fe`

## pseudocode

```c
__int64 __fastcall CMountPoint::_RemoveLocalMountPoint(LPCWSTR lpString2)
{
  __int64 v2; // rax
  CDriveLetterCache *v3; // rdi
  int DriveNumberW; // eax
  struct CMountPoint **DriveLetterData; // rax
  CDriveLetterCache *v6; // rcx
  struct CMountPoint **v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  void *v9; // rax
  _DWORD *v10; // rsi
  int i; // edi
  __int64 v12; // rax
  WCHAR *Ptr; // rax
  CMountPoint *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax

  if ( (unsigned int)CMountPoint::IsDriveLetter(lpString2) )
  {
    v2 = Global_WindowsStorage_Untyped_MountPoint();
    CCritSecDelayInitBase::Enter((PVOID)(v2 + 56));
    v3 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint() + 264);
    DriveNumberW = PathGetDriveNumberW(lpString2);
    DriveLetterData = (struct CMountPoint **)CDriveLetterCache::GetDriveLetterData(v3, DriveNumberW);
    v7 = DriveLetterData;
    if ( DriveLetterData )
    {
      CDriveLetterCache::RemovePathLookupEntry(v6, *DriveLetterData);
      SafeRelease<CMtPtRemote>(v7);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)(Global_WindowsStorage_Untyped_MountPoint() + 56);
  }
  else
  {
    v9 = (void *)Global_WindowsStorage_Untyped_MountPoint();
    CCritSecDelayInitBase::Enter(v9);
    v10 = *(_DWORD **)(Global_WindowsStorage_Untyped_MountPoint() + 240);
    if ( v10 )
      LODWORD(v10) = *v10;
    for ( i = 0; i < (int)v10; ++i )
    {
      v12 = Global_WindowsStorage_Untyped_MountPoint();
      Ptr = (WCHAR *)DPA_GetPtr(*(HDPA *)(v12 + 240), i);
      v14 = (CMountPoint *)Ptr;
      if ( Ptr && !lstrcmpiW(Ptr + 26, lpString2) )
      {
        CMountPoint::Release(v14);
        v15 = Global_WindowsStorage_Untyped_MountPoint();
        DPA_DeletePtr(*(HDPA *)(v15 + 240), i);
        break;
      }
    }
    if ( (unsigned int)IsDesktopExplorerProcess() )
    {
      v16 = Global_WindowsStorage_Untyped_MountPoint();
      (*(void (__fastcall **)(__int64, _QWORD, LPCWSTR))(*(_QWORD *)(v16 + 1176) + 24LL))(v16 + 1176, 0, lpString2);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_Untyped_MountPoint();
  }
  LeaveCriticalSection(v8);
  return 0;
}

```

## disassembly

```asm
0x1801db8e4  push    rbx
0x1801db8e6  push    rbp
0x1801db8e7  push    rsi
0x1801db8e8  push    rdi
0x1801db8e9  sub     rsp, 28h
0x1801db8ed  mov     rbp, rcx
0x1801db8f0  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x1801db8f5  test    eax, eax
0x1801db8f7  jz      short loc_1801DB967
0x1801db8f9  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db900  nop     dword ptr [rax+rax+00h]
0x1801db905  lea     rcx, [rax+38h]; Parameter
0x1801db909  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1801db90e  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db915  nop     dword ptr [rax+rax+00h]
0x1801db91a  mov     rcx, rbp; pszPath
0x1801db91d  lea     rdi, [rax+108h]
0x1801db924  call    cs:__imp_PathGetDriveNumberW
0x1801db92b  nop     dword ptr [rax+rax+00h]
0x1801db930  mov     edx, eax; int
0x1801db932  mov     rcx, rdi; this
0x1801db935  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x1801db93a  mov     rbx, rax
0x1801db93d  test    rax, rax
0x1801db940  jz      short loc_1801DB952
0x1801db942  mov     rdx, [rax]; struct CMountPoint *
0x1801db945  call    ?RemovePathLookupEntry@CDriveLetterCache@@QEAAXPEAVCMountPoint@@@Z; CDriveLetterCache::RemovePathLookupEntry(CMountPoint *)
0x1801db94a  mov     rcx, rbx
0x1801db94d  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x1801db952  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db959  nop     dword ptr [rax+rax+00h]
0x1801db95e  lea     rcx, [rax+38h]
0x1801db962  jmp     loc_1801DBA41
0x1801db967  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db96e  nop     dword ptr [rax+rax+00h]
0x1801db973  mov     rcx, rax; Parameter
0x1801db976  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1801db97b  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db982  nop     dword ptr [rax+rax+00h]
0x1801db987  mov     rsi, [rax+0F0h]
0x1801db98e  test    rsi, rsi
0x1801db991  jz      short loc_1801DB995
0x1801db993  mov     esi, [rsi]
0x1801db995  xor     edi, edi
0x1801db997  cmp     edi, esi
0x1801db999  jge     short loc_1801DB9FE
0x1801db99b  movsxd  rbx, edi
0x1801db99e  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db9a5  nop     dword ptr [rax+rax+00h]
0x1801db9aa  mov     rdx, rbx; i
0x1801db9ad  mov     rcx, [rax+0F0h]; hdpa
0x1801db9b4  call    DPA_GetPtr
0x1801db9b9  mov     rbx, rax
0x1801db9bc  test    rax, rax
0x1801db9bf  jz      short loc_1801DB9D8
0x1801db9c1  lea     rcx, [rax+34h]; lpString1
0x1801db9c5  mov     rdx, rbp; lpString2
0x1801db9c8  call    cs:__imp_lstrcmpiW
0x1801db9cf  nop     dword ptr [rax+rax+00h]
0x1801db9d4  test    eax, eax
0x1801db9d6  jz      short loc_1801DB9DC
0x1801db9d8  inc     edi
0x1801db9da  jmp     short loc_1801DB997
0x1801db9dc  mov     rcx, rbx; this
0x1801db9df  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1801db9e4  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801db9eb  nop     dword ptr [rax+rax+00h]
0x1801db9f0  mov     edx, edi; i
0x1801db9f2  mov     rcx, [rax+0F0h]; hdpa
0x1801db9f9  call    DPA_DeletePtr
0x1801db9fe  call    cs:__imp_IsDesktopExplorerProcess
0x1801dba05  nop     dword ptr [rax+rax+00h]
0x1801dba0a  test    eax, eax
0x1801dba0c  jz      short loc_1801DBA32
0x1801dba0e  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801dba15  nop     dword ptr [rax+rax+00h]
0x1801dba1a  mov     r8, rbp
0x1801dba1d  xor     edx, edx
0x1801dba1f  lea     rcx, [rax+498h]
0x1801dba26  mov     rax, [rcx]
0x1801dba29  mov     rax, [rax+18h]
0x1801dba2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dba32  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1801dba39  nop     dword ptr [rax+rax+00h]
0x1801dba3e  mov     rcx, rax; lpCriticalSection
0x1801dba41  call    cs:__imp_LeaveCriticalSection
0x1801dba48  nop     dword ptr [rax+rax+00h]
0x1801dba4d  xor     eax, eax
0x1801dba4f  add     rsp, 28h
0x1801dba53  pop     rdi
0x1801dba54  pop     rsi
0x1801dba55  pop     rbp
0x1801dba56  pop     rbx
0x1801dba57  retn
```
