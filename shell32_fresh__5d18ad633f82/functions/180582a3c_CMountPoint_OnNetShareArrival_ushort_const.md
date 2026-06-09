# CMountPoint::OnNetShareArrival(ushort const *)

- ea: `0x180582a3c`
- end: `0x180582ce9`
- name: `?OnNetShareArrival@CMountPoint@@SAXPEBG@Z`
- size: `685`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e91bc`

## callees

- `0x18001a2bc`
- `0x18001aa98`
- `0x1800dbe2c`
- `0x1800dec34`
- `0x1801928f0`
- `0x1801eeadc`
- `0x180249490`
- `0x180289340`
- `0x180582a3c`
- `0x180584b34`
- `0x180584c20`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180582ba7`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180582ba7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582b10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582b10`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582ada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582b5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582ada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582b5b`
- `MPR!WNetGetConnectionW` at `0x180582b85`
- `MPR!WNetGetConnectionW` at `0x180582b85`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582a93`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582aa8`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582ac4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582b00`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582b1c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c18`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c59`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c6d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582a93`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582aa8`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582ac4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582b00`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582b1c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c18`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c59`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582c6d`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582bda`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582bda`
- `Windows.Storage!ShellExecuteW` at `0x180582c4d`
- `Windows.Storage!ShellExecuteW` at `0x180582c4d`

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
0x180582a3c  push    rbp
0x180582a3e  push    rbx
0x180582a3f  push    rsi
0x180582a40  push    rdi
0x180582a41  push    r12
0x180582a43  push    r14
0x180582a45  lea     rbp, [rsp-178h]
0x180582a4d  sub     rsp, 278h
0x180582a54  mov     rax, cs:__security_cookie
0x180582a5b  xor     rax, rsp
0x180582a5e  mov     [rbp+1A0h+var_40], rax
0x180582a65  mov     r12d, 1
0x180582a6b  mov     rdi, rcx
0x180582a6e  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x180582a75  jz      short loc_180582A90
0x180582a77  lea     rax, [rsp+2A0h+var_268]
0x180582a7c  mov     r9d, r12d
0x180582a7f  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Start
0x180582a86  mov     [rsp+2A0h+lpDirectory], rax
0x180582a8b  call    McGenEventWrite_EventWriteTransfer
0x180582a90  xor     sil, sil
0x180582a93  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582a9a  nop     dword ptr [rax+rax+00h]
0x180582a9f  lea     rcx, [rax+38h]; Parameter
0x180582aa3  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180582aa8  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582aaf  nop     dword ptr [rax+rax+00h]
0x180582ab4  cmp     dword ptr [rax+450h], 0
0x180582abb  jnz     short loc_180582AC4
0x180582abd  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x180582ac2  jmp     short loc_180582B00
0x180582ac4  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582acb  nop     dword ptr [rax+rax+00h]
0x180582ad0  mov     rcx, rdi; pszPath
0x180582ad3  lea     rbx, [rax+108h]
0x180582ada  call    cs:__imp_PathGetDriveNumberW
0x180582ae1  nop     dword ptr [rax+rax+00h]
0x180582ae6  mov     edx, eax; int
0x180582ae8  mov     rcx, rbx; this
0x180582aeb  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x180582af0  test    rax, rax
0x180582af3  jz      short loc_180582B00
0x180582af5  mov     rcx, rax; this
0x180582af8  mov     sil, r12b
0x180582afb  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x180582b00  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582b07  nop     dword ptr [rax+rax+00h]
0x180582b0c  lea     rcx, [rax+38h]; lpCriticalSection
0x180582b10  call    cs:__imp_LeaveCriticalSection
0x180582b17  nop     dword ptr [rax+rax+00h]
0x180582b1c  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582b23  nop     dword ptr [rax+rax+00h]
0x180582b28  cmp     dword ptr [rax+450h], 0
0x180582b2f  jz      loc_180582CA7
0x180582b35  test    sil, sil
0x180582b38  jnz     loc_180582CA7
0x180582b3e  mov     eax, 41h ; 'A'
0x180582b43  mov     [rsp+2A0h+var_256], 3Ah ; ':'
0x180582b4b  mov     rcx, rdi; pszPath
0x180582b4e  mov     [rsp+2A0h+LocalName], ax
0x180582b53  mov     [rsp+2A0h+nLength], 104h
0x180582b5b  call    cs:__imp_PathGetDriveNumberW
0x180582b62  nop     dword ptr [rax+rax+00h]
0x180582b67  movzx   ecx, word ptr [rdi]
0x180582b6a  lea     r8, [rsp+2A0h+nLength]; lpnLength
0x180582b6f  mov     [rsp+2A0h+LocalName], cx
0x180582b74  lea     rdx, [rsp+2A0h+RemoteName]; lpRemoteName
0x180582b79  mov     ecx, eax
0x180582b7b  mov     ebx, r12d
0x180582b7e  shl     ebx, cl
0x180582b80  lea     rcx, [rsp+2A0h+LocalName]; lpLocalName
0x180582b85  call    cs:__imp_WNetGetConnectionW
0x180582b8c  nop     dword ptr [rax+rax+00h]
0x180582b91  test    eax, eax
0x180582b93  jnz     short loc_180582BA7
0x180582b95  mov     r8d, r12d; int
0x180582b98  lea     rdx, [rsp+2A0h+RemoteName]; pszSrch
0x180582b9d  mov     rcx, rdi; unsigned __int16 *
0x180582ba0  call    ?_CreateMtPtRemote@CMtPtRemote@@CAJPEBG0H@Z; CMtPtRemote::_CreateMtPtRemote(ushort const *,ushort const *,int)
0x180582ba5  jmp     short loc_180582BC3
0x180582ba7  call    cs:__imp_GetLogicalDrives
0x180582bae  nop     dword ptr [rax+rax+00h]
0x180582bb3  test    ebx, eax
0x180582bb5  jz      loc_180582CA7
0x180582bbb  mov     rcx, rdi; unsigned __int16 *
0x180582bbe  call    ?_CreateMtPtRemoteWithoutShareName@CMtPtRemote@@CAJPEBG@Z; CMtPtRemote::_CreateMtPtRemoteWithoutShareName(ushort const *)
0x180582bc3  test    eax, eax
0x180582bc5  js      loc_180582CA7
0x180582bcb  xor     r9d, r9d; dwItem2
0x180582bce  mov     r8, rdi; dwItem1
0x180582bd1  mov     ecx, 100h; wEventId
0x180582bd6  lea     edx, [r9+5]; uFlags
0x180582bda  call    cs:__imp_SHChangeNotify
0x180582be1  nop     dword ptr [rax+rax+00h]
0x180582be6  lea     rax, [rsp+2A0h+var_270]
0x180582beb  mov     [rsp+2A0h+var_270], 0
0x180582bf3  xor     r9d, r9d; unsigned int
0x180582bf6  mov     [rsp+2A0h+lpDirectory], rax; int *
0x180582bfb  lea     r8, aAutorun_0; "AutoRun"
0x180582c02  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180582c09  lea     rdx, aSoftwareMicros_116; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180582c10  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180582c15  mov     r14d, eax
0x180582c18  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582c1f  nop     dword ptr [rax+rax+00h]
0x180582c24  mov     esi, [rsp+2A0h+var_270]
0x180582c28  test    [rax+528h], ebx
0x180582c2e  jnz     short loc_180582C39
0x180582c30  test    r14d, r14d
0x180582c33  js      short loc_180582CA7
0x180582c35  test    esi, esi
0x180582c37  jz      short loc_180582CA7
0x180582c39  mov     [rsp+2A0h+nShowCmd], r12d; nShowCmd
0x180582c3e  mov     r9, rdi; lpParameters
0x180582c41  mov     r8, rdi; lpFile
0x180582c44  mov     [rsp+2A0h+lpDirectory], rdi; lpDirectory
0x180582c49  xor     edx, edx; lpOperation
0x180582c4b  xor     ecx, ecx; hwnd
0x180582c4d  call    cs:__imp_ShellExecuteW
0x180582c54  nop     dword ptr [rax+rax+00h]
0x180582c59  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582c60  nop     dword ptr [rax+rax+00h]
0x180582c65  test    [rax+528h], ebx
0x180582c6b  jz      short loc_180582C81
0x180582c6d  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582c74  nop     dword ptr [rax+rax+00h]
0x180582c79  not     ebx
0x180582c7b  and     [rax+528h], ebx
0x180582c81  test    r14d, r14d
0x180582c84  js      short loc_180582CA7
0x180582c86  test    esi, esi
0x180582c88  jz      short loc_180582CA7
0x180582c8a  xor     r9d, r9d; int
0x180582c8d  lea     r8, aAutorun_0; "AutoRun"
0x180582c94  lea     rdx, aSoftwareMicros_116; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180582c9b  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180582ca2  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x180582ca7  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x180582cae  jz      short loc_180582CC9
0x180582cb0  lea     rax, [rsp+2A0h+var_268]
0x180582cb5  mov     r9d, r12d
0x180582cb8  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareArrival_Stop
0x180582cbf  mov     [rsp+2A0h+lpDirectory], rax
0x180582cc4  call    McGenEventWrite_EventWriteTransfer
0x180582cc9  mov     rcx, [rbp+1A0h+var_40]
0x180582cd0  xor     rcx, rsp; StackCookie
0x180582cd3  call    __security_check_cookie
0x180582cd8  add     rsp, 278h
0x180582cdf  pop     r14
0x180582ce1  pop     r12
0x180582ce3  pop     rdi
0x180582ce4  pop     rsi
0x180582ce5  pop     rbx
0x180582ce6  pop     rbp
0x180582ce7  retn
```
