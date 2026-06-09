# CMountPoint::OnNetShareRemoval(ushort const *)

- ea: `0x180582cf0`
- end: `0x180582efb`
- name: `?OnNetShareRemoval@CMountPoint@@SAXPEBG@Z`
- size: `523`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1801e91bc`

## callees

- `0x18001a064`
- `0x18001a2bc`
- `0x18001a2fc`
- `0x18001aa98`
- `0x18009a63c`
- `0x1800dbe2c`
- `0x1801928f0`
- `0x1801eeadc`
- `0x180249490`
- `0x180265730`
- `0x180582cf0`
- `0x180584940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582e3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582e3b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582daf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582e12`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582daf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582e12`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d35`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d4a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d64`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d80`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d99`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582de7`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582dfc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582e2b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d35`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d4a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d64`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d80`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582d99`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582de7`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582dfc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582e2b`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582e56`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582ea2`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582e56`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180582ea2`

## pseudocode

```c
void __fastcall CMountPoint::OnNetShareRemoval(const unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  CDriveLetterCache *v8; // rbx
  int DriveNumberW; // eax
  CMtPtRemote *Remote; // rax
  CMountPoint *v11; // rsi
  int IsUnavailableNetDrive; // ebx
  __int64 v13; // rax
  CDriveLetterCache *v14; // rbx
  int v15; // eax
  __int64 v16; // rax
  CMountPoint *v17[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Start, a3, 1, v17);
  v4 = Global_WindowsStorage_Untyped_MountPoint();
  CCritSecDelayInitBase::Enter((PVOID)(v4 + 56));
  if ( !*(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1104) )
    CMountPoint::_InitNetDrives();
  v5 = Global_WindowsStorage_Untyped_MountPoint();
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 56));
  if ( *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1104) )
  {
    v8 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint() + 264);
    DriveNumberW = PathGetDriveNumberW(a1);
    Remote = CDriveLetterCache::GetRemote(v8, DriveNumberW);
    v11 = Remote;
    if ( !Remote
      || (IsUnavailableNetDrive = CMtPtRemote::IsUnavailableNetDrive(Remote),
          CMountPoint::Release(v11),
          !IsUnavailableNetDrive) )
    {
      v13 = Global_WindowsStorage_Untyped_MountPoint();
      CCritSecDelayInitBase::Enter((PVOID)(v13 + 56));
      v14 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint() + 264);
      v15 = PathGetDriveNumberW(a1);
      CDriveLetterCache::SetRemote(v14, v15, 0);
      v16 = Global_WindowsStorage_Untyped_MountPoint();
      LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 56));
      SHChangeNotify(128, 5u, a1, 0);
      v17[0] = 0;
      if ( (int)CMountPoint::GetMountPoint(a1, 0, v17) >= 0 )
      {
        if ( (unsigned int)CMountPoint::IsDriveLetter(a1) )
          CDBurn_OnDeviceChange(1, a1);
        SHChangeNotify(256, 5u, a1, 0);
        CMountPoint::Release(v17[0]);
      }
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Stop, v7, 1, v17);
}

```

## disassembly

```asm
0x180582cf0  mov     r11, rsp
0x180582cf3  mov     [r11+10h], rbx
0x180582cf7  mov     [r11+18h], rsi
0x180582cfb  push    rdi
0x180582cfc  sub     rsp, 50h
0x180582d00  mov     rax, cs:__security_cookie
0x180582d07  xor     rax, rsp
0x180582d0a  mov     [rsp+58h+var_18], rax
0x180582d0f  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180582d16  mov     rdi, rcx
0x180582d19  jz      short loc_180582D35
0x180582d1b  lea     rax, [r11-28h]
0x180582d1f  mov     r9d, 1
0x180582d25  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Start
0x180582d2c  mov     [r11-38h], rax
0x180582d30  call    McGenEventWrite_EventWriteTransfer
0x180582d35  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582d3c  nop     dword ptr [rax+rax+00h]
0x180582d41  lea     rcx, [rax+38h]; Parameter
0x180582d45  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180582d4a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582d51  nop     dword ptr [rax+rax+00h]
0x180582d56  cmp     dword ptr [rax+450h], 0
0x180582d5d  jnz     short loc_180582D64
0x180582d5f  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x180582d64  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582d6b  nop     dword ptr [rax+rax+00h]
0x180582d70  lea     rcx, [rax+38h]; lpCriticalSection
0x180582d74  call    cs:__imp_LeaveCriticalSection
0x180582d7b  nop     dword ptr [rax+rax+00h]
0x180582d80  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582d87  nop     dword ptr [rax+rax+00h]
0x180582d8c  cmp     dword ptr [rax+450h], 0
0x180582d93  jz      loc_180582EB8
0x180582d99  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582da0  nop     dword ptr [rax+rax+00h]
0x180582da5  mov     rcx, rdi; pszPath
0x180582da8  lea     rbx, [rax+108h]
0x180582daf  call    cs:__imp_PathGetDriveNumberW
0x180582db6  nop     dword ptr [rax+rax+00h]
0x180582dbb  mov     edx, eax; int
0x180582dbd  mov     rcx, rbx; this
0x180582dc0  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x180582dc5  mov     rsi, rax
0x180582dc8  test    rax, rax
0x180582dcb  jz      short loc_180582DE7
0x180582dcd  mov     rcx, rax; this
0x180582dd0  call    ?IsUnavailableNetDrive@CMtPtRemote@@UEAAHXZ; CMtPtRemote::IsUnavailableNetDrive(void)
0x180582dd5  mov     rcx, rsi; this
0x180582dd8  mov     ebx, eax
0x180582dda  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x180582ddf  test    ebx, ebx
0x180582de1  jnz     loc_180582EB8
0x180582de7  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582dee  nop     dword ptr [rax+rax+00h]
0x180582df3  lea     rcx, [rax+38h]; Parameter
0x180582df7  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180582dfc  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582e03  nop     dword ptr [rax+rax+00h]
0x180582e08  mov     rcx, rdi; pszPath
0x180582e0b  lea     rbx, [rax+108h]
0x180582e12  call    cs:__imp_PathGetDriveNumberW
0x180582e19  nop     dword ptr [rax+rax+00h]
0x180582e1e  xor     r8d, r8d; struct CMtPtRemote *
0x180582e21  mov     rcx, rbx; this
0x180582e24  mov     edx, eax; int
0x180582e26  call    ?SetRemote@CDriveLetterCache@@QEAAXHPEAVCMtPtRemote@@@Z; CDriveLetterCache::SetRemote(int,CMtPtRemote *)
0x180582e2b  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582e32  nop     dword ptr [rax+rax+00h]
0x180582e37  lea     rcx, [rax+38h]; lpCriticalSection
0x180582e3b  call    cs:__imp_LeaveCriticalSection
0x180582e42  nop     dword ptr [rax+rax+00h]
0x180582e47  xor     r9d, r9d; dwItem2
0x180582e4a  mov     r8, rdi; dwItem1
0x180582e4d  lea     ebx, [r9+5]
0x180582e51  mov     edx, ebx; uFlags
0x180582e53  lea     ecx, [rbx+7Bh]; wEventId
0x180582e56  call    cs:__imp_SHChangeNotify
0x180582e5d  nop     dword ptr [rax+rax+00h]
0x180582e62  lea     r8, [rsp+58h+var_28]
0x180582e67  mov     [rsp+58h+var_28], 0
0x180582e70  xor     edx, edx
0x180582e72  mov     rcx, rdi
0x180582e75  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x180582e7a  test    eax, eax
0x180582e7c  js      short loc_180582EB8
0x180582e7e  mov     rcx, rdi; unsigned __int16 *
0x180582e81  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x180582e86  test    eax, eax
0x180582e88  jz      short loc_180582E95
0x180582e8a  mov     rdx, rdi; unsigned __int16 *
0x180582e8d  lea     ecx, [rbx-4]; int
0x180582e90  call    ?CDBurn_OnDeviceChange@@YAJHPEBG@Z; CDBurn_OnDeviceChange(int,ushort const *)
0x180582e95  xor     r9d, r9d; dwItem2
0x180582e98  mov     r8, rdi; dwItem1
0x180582e9b  mov     edx, ebx; uFlags
0x180582e9d  mov     ecx, 100h; wEventId
0x180582ea2  call    cs:__imp_SHChangeNotify
0x180582ea9  nop     dword ptr [rax+rax+00h]
0x180582eae  mov     rcx, [rsp+58h+var_28]; this
0x180582eb3  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x180582eb8  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180582ebf  jz      short loc_180582EDD
0x180582ec1  lea     rax, [rsp+58h+var_28]
0x180582ec6  mov     r9d, 1
0x180582ecc  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Stop
0x180582ed3  mov     [rsp+58h+var_38], rax
0x180582ed8  call    McGenEventWrite_EventWriteTransfer
0x180582edd  mov     rcx, [rsp+58h+var_18]
0x180582ee2  xor     rcx, rsp; StackCookie
0x180582ee5  call    __security_check_cookie
0x180582eea  mov     rbx, [rsp+58h+arg_8]
0x180582eef  mov     rsi, [rsp+58h+arg_10]
0x180582ef4  add     rsp, 50h
0x180582ef8  pop     rdi
0x180582ef9  retn
```
