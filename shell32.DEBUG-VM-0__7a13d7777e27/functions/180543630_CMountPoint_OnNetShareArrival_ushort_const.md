# CMountPoint::OnNetShareArrival(ushort const *)

- ea: `0x180543630`
- end: `0x180543882`
- name: `?OnNetShareArrival@CMountPoint@@SAXPEBG@Z`
- size: `594`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801d1fb0`

## callees

- `0x1800681a8`
- `0x18008cad4`
- `0x1800bfb48`
- `0x1800c0204`
- `0x180180a3c`
- `0x1801d7910`
- `0x180233280`
- `0x18027075c`
- `0x180543630`
- `0x180545408`
- `0x1805454d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180543765`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180543765`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805436e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805436e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805436bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543725`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1805436bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543725`
- `MPR!WNetGetConnectionW` at `0x180543749`
- `MPR!WNetGetConnectionW` at `0x180543749`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543687`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543696`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436ac`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436dc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436ec`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805437ca`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805437ff`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054380d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543687`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543696`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436ac`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436dc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805436ec`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805437ca`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805437ff`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054380d`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180543792`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180543792`
- `Windows.Storage!ShellExecuteW` at `0x1805437f9`
- `Windows.Storage!ShellExecuteW` at `0x1805437f9`

## pseudocode

```c
void __fastcall CMountPoint::OnNetShareArrival(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  char v4; // si
  __int64 v5; // rax
  CDriveLetterCache *v6; // rbx
  int DriveNumberW; // eax
  CMountPoint *Remote; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  char v12; // al
  int v13; // ebx
  int MtPtRemoteWithoutShareName; // eax
  int BOOLWithREGSAM; // r14d
  __int64 v16; // rax
  int v17; // esi
  __int64 v18; // rax
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nLength; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR LocalName[4]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR RemoteName[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Start, a3, 1, v21);
  v4 = 0;
  v5 = Global_WindowsStorage_Untyped_MountPoint();
  CCritSecDelayInitBase::Enter((PVOID)(v5 + 56));
  if ( *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1104) )
  {
    v6 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint() + 264);
    DriveNumberW = PathGetDriveNumberW(a1);
    Remote = CDriveLetterCache::GetRemote(v6, DriveNumberW);
    if ( Remote )
    {
      v4 = 1;
      CMountPoint::Release(Remote);
    }
  }
  else
  {
    CMountPoint::_InitNetDrives();
  }
  v9 = Global_WindowsStorage_Untyped_MountPoint();
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 56));
  if ( *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1104) && !v4 )
  {
    wcscpy(LocalName, L"A:");
    nLength = 260;
    v12 = PathGetDriveNumberW(a1);
    LocalName[0] = *a1;
    v13 = 1 << v12;
    if ( WNetGetConnectionW(LocalName, RemoteName, &nLength) )
    {
      if ( (GetLogicalDrives() & v13) == 0 )
        goto LABEL_22;
      MtPtRemoteWithoutShareName = CMtPtRemote::_CreateMtPtRemoteWithoutShareName(a1);
    }
    else
    {
      MtPtRemoteWithoutShareName = CMtPtRemote::_CreateMtPtRemote(a1, RemoteName, 1);
    }
    if ( MtPtRemoteWithoutShareName >= 0 )
    {
      SHChangeNotify(256, 5u, a1, 0);
      v19 = 0;
      BOOLWithREGSAM = SHRegGetBOOLWithREGSAM(
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\MapNetworkDrive",
                         L"AutoRun",
                         0,
                         &v19);
      v16 = Global_WindowsStorage_Untyped_MountPoint();
      v17 = v19;
      if ( (v13 & *(_DWORD *)(v16 + 1320)) != 0 || BOOLWithREGSAM >= 0 && v19 )
      {
        ShellExecuteW(0, 0, a1, a1, a1, 1);
        if ( (v13 & *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1320)) != 0 )
        {
          v18 = Global_WindowsStorage_Untyped_MountPoint();
          *(_DWORD *)(v18 + 1320) &= ~v13;
        }
        if ( BOOLWithREGSAM >= 0 && v17 )
          SHRegSetBOOL(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\MapNetworkDrive",
            L"AutoRun",
            0);
      }
    }
  }
LABEL_22:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Stop, v11, 1, v21);
}

```

## disassembly

```asm
0x180543630  push    rbp
0x180543632  push    rbx
0x180543633  push    rsi
0x180543634  push    rdi
0x180543635  push    r12
0x180543637  push    r14
0x180543639  lea     rbp, [rsp-178h]
0x180543641  sub     rsp, 278h
0x180543648  mov     rax, cs:__security_cookie
0x18054364f  xor     rax, rsp
0x180543652  mov     [rbp+1A0h+var_40], rax
0x180543659  mov     r12d, 1
0x18054365f  mov     rdi, rcx
0x180543662  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x180543669  jz      short loc_180543684
0x18054366b  lea     rax, [rsp+2A0h+var_268]
0x180543670  mov     r9d, r12d
0x180543673  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Start
0x18054367a  mov     [rsp+2A0h+lpDirectory], rax
0x18054367f  call    McGenEventWrite_EventWriteTransfer
0x180543684  xor     sil, sil
0x180543687  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054368d  lea     rcx, [rax+38h]; Parameter
0x180543691  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180543696  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054369c  cmp     dword ptr [rax+450h], 0
0x1805436a3  jnz     short loc_1805436AC
0x1805436a5  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x1805436aa  jmp     short loc_1805436DC
0x1805436ac  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805436b2  mov     rcx, rdi; pszPath
0x1805436b5  lea     rbx, [rax+108h]
0x1805436bc  call    cs:__imp_PathGetDriveNumberW
0x1805436c2  mov     edx, eax; int
0x1805436c4  mov     rcx, rbx; this
0x1805436c7  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x1805436cc  test    rax, rax
0x1805436cf  jz      short loc_1805436DC
0x1805436d1  mov     rcx, rax; this
0x1805436d4  mov     sil, r12b
0x1805436d7  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1805436dc  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805436e2  lea     rcx, [rax+38h]; lpCriticalSection
0x1805436e6  call    cs:__imp_LeaveCriticalSection
0x1805436ec  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805436f2  cmp     dword ptr [rax+450h], 0
0x1805436f9  jz      loc_180543841
0x1805436ff  test    sil, sil
0x180543702  jnz     loc_180543841
0x180543708  mov     eax, 41h ; 'A'
0x18054370d  mov     [rsp+2A0h+var_256], 3Ah ; ':'
0x180543715  mov     rcx, rdi; pszPath
0x180543718  mov     [rsp+2A0h+LocalName], ax
0x18054371d  mov     [rsp+2A0h+nLength], 104h
0x180543725  call    cs:__imp_PathGetDriveNumberW
0x18054372b  movzx   ecx, word ptr [rdi]
0x18054372e  lea     r8, [rsp+2A0h+nLength]; lpnLength
0x180543733  mov     [rsp+2A0h+LocalName], cx
0x180543738  lea     rdx, [rsp+2A0h+RemoteName]; lpRemoteName
0x18054373d  mov     ecx, eax
0x18054373f  mov     ebx, r12d
0x180543742  shl     ebx, cl
0x180543744  lea     rcx, [rsp+2A0h+LocalName]; lpLocalName
0x180543749  call    cs:__imp_WNetGetConnectionW
0x18054374f  test    eax, eax
0x180543751  jnz     short loc_180543765
0x180543753  mov     r8d, r12d; int
0x180543756  lea     rdx, [rsp+2A0h+RemoteName]; pszSrch
0x18054375b  mov     rcx, rdi; unsigned __int16 *
0x18054375e  call    ?_CreateMtPtRemote@CMtPtRemote@@CAJPEBG0H@Z; CMtPtRemote::_CreateMtPtRemote(ushort const *,ushort const *,int)
0x180543763  jmp     short loc_18054377B
0x180543765  call    cs:__imp_GetLogicalDrives
0x18054376b  test    ebx, eax
0x18054376d  jz      loc_180543841
0x180543773  mov     rcx, rdi; unsigned __int16 *
0x180543776  call    ?_CreateMtPtRemoteWithoutShareName@CMtPtRemote@@CAJPEBG@Z; CMtPtRemote::_CreateMtPtRemoteWithoutShareName(ushort const *)
0x18054377b  test    eax, eax
0x18054377d  js      loc_180543841
0x180543783  xor     r9d, r9d; dwItem2
0x180543786  mov     r8, rdi; dwItem1
0x180543789  mov     ecx, 100h; wEventId
0x18054378e  lea     edx, [r9+5]; uFlags
0x180543792  call    cs:__imp_SHChangeNotify
0x180543798  lea     rax, [rsp+2A0h+var_270]
0x18054379d  mov     [rsp+2A0h+var_270], 0
0x1805437a5  xor     r9d, r9d; unsigned int
0x1805437a8  mov     [rsp+2A0h+lpDirectory], rax; int *
0x1805437ad  lea     r8, aAutorun_0; "AutoRun"
0x1805437b4  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1805437bb  lea     rdx, aSoftwareMicros_116; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805437c2  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1805437c7  mov     r14d, eax
0x1805437ca  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805437d0  mov     esi, [rsp+2A0h+var_270]
0x1805437d4  test    [rax+528h], ebx
0x1805437da  jnz     short loc_1805437E5
0x1805437dc  test    r14d, r14d
0x1805437df  js      short loc_180543841
0x1805437e1  test    esi, esi
0x1805437e3  jz      short loc_180543841
0x1805437e5  mov     [rsp+2A0h+nShowCmd], r12d; nShowCmd
0x1805437ea  mov     r9, rdi; lpParameters
0x1805437ed  mov     r8, rdi; lpFile
0x1805437f0  mov     [rsp+2A0h+lpDirectory], rdi; lpDirectory
0x1805437f5  xor     edx, edx; lpOperation
0x1805437f7  xor     ecx, ecx; hwnd
0x1805437f9  call    cs:__imp_ShellExecuteW
0x1805437ff  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180543805  test    [rax+528h], ebx
0x18054380b  jz      short loc_18054381B
0x18054380d  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180543813  not     ebx
0x180543815  and     [rax+528h], ebx
0x18054381b  test    r14d, r14d
0x18054381e  js      short loc_180543841
0x180543820  test    esi, esi
0x180543822  jz      short loc_180543841
0x180543824  xor     r9d, r9d; int
0x180543827  lea     r8, aAutorun_0; "AutoRun"
0x18054382e  lea     rdx, aSoftwareMicros_116; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180543835  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18054383c  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x180543841  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x180543848  jz      short loc_180543863
0x18054384a  lea     rax, [rsp+2A0h+var_268]
0x18054384f  mov     r9d, r12d
0x180543852  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Stop
0x180543859  mov     [rsp+2A0h+lpDirectory], rax
0x18054385e  call    McGenEventWrite_EventWriteTransfer
0x180543863  mov     rcx, [rbp+1A0h+var_40]
0x18054386a  xor     rcx, rsp; StackCookie
0x18054386d  call    __security_check_cookie
0x180543872  add     rsp, 278h
0x180543879  pop     r14
0x18054387b  pop     r12
0x18054387d  pop     rdi
0x18054387e  pop     rsi
0x18054387f  pop     rbx
0x180543880  pop     rbp
0x180543881  retn
```
