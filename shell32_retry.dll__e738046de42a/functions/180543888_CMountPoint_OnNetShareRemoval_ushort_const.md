# CMountPoint::OnNetShareRemoval(ushort const *)

- ea: `0x180543888`
- end: `0x180543a3e`
- name: `?OnNetShareRemoval@CMountPoint@@SAXPEBG@Z`
- size: `438`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1801d1fb0`

## callees

- `0x18008cad4`
- `0x1800bf924`
- `0x1800bfb48`
- `0x1800bfb80`
- `0x1800c0204`
- `0x1800c0e20`
- `0x180180a3c`
- `0x1801d7910`
- `0x180233280`
- `0x18024eadc`
- `0x180543888`
- `0x180545230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805438fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180543991`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805438fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180543991`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543923`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543974`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543923`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180543974`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438cd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438dc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438f0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543900`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543913`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543955`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543964`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543987`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438cd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438dc`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805438f0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543900`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543913`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543955`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543964`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543987`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805439a6`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805439ec`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805439a6`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805439ec`

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
    McGenEventWrite_EventWriteTransfer(a1, &Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Start, a3, 1, v17);
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
    McGenEventWrite_EventWriteTransfer(v6, &Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Stop, v7, 1, v17);
}

```

## disassembly

```asm
0x180543888  mov     r11, rsp
0x18054388b  mov     [r11+10h], rbx
0x18054388f  mov     [r11+18h], rsi
0x180543893  push    rdi
0x180543894  sub     rsp, 50h
0x180543898  mov     rax, cs:__security_cookie
0x18054389f  xor     rax, rsp
0x1805438a2  mov     [rsp+58h+var_18], rax
0x1805438a7  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1805438ae  mov     rdi, rcx
0x1805438b1  jz      short loc_1805438CD
0x1805438b3  lea     rax, [r11-28h]
0x1805438b7  mov     r9d, 1
0x1805438bd  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Start
0x1805438c4  mov     [r11-38h], rax
0x1805438c8  call    McGenEventWrite_EventWriteTransfer
0x1805438cd  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805438d3  lea     rcx, [rax+38h]; Parameter
0x1805438d7  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1805438dc  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805438e2  cmp     dword ptr [rax+450h], 0
0x1805438e9  jnz     short loc_1805438F0
0x1805438eb  call    ?_InitNetDrives@CMountPoint@@CAJXZ; CMountPoint::_InitNetDrives(void)
0x1805438f0  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805438f6  lea     rcx, [rax+38h]; lpCriticalSection
0x1805438fa  call    cs:__imp_LeaveCriticalSection
0x180543900  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180543906  cmp     dword ptr [rax+450h], 0
0x18054390d  jz      loc_1805439FC
0x180543913  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180543919  mov     rcx, rdi; pszPath
0x18054391c  lea     rbx, [rax+108h]
0x180543923  call    cs:__imp_PathGetDriveNumberW
0x180543929  mov     edx, eax; int
0x18054392b  mov     rcx, rbx; this
0x18054392e  call    ?GetRemote@CDriveLetterCache@@QEAAPEAVCMtPtRemote@@H@Z; CDriveLetterCache::GetRemote(int)
0x180543933  mov     rsi, rax
0x180543936  test    rax, rax
0x180543939  jz      short loc_180543955
0x18054393b  mov     rcx, rax; this
0x18054393e  call    ?IsUnavailableNetDrive@CMtPtRemote@@UEAAHXZ; CMtPtRemote::IsUnavailableNetDrive(void)
0x180543943  mov     rcx, rsi; this
0x180543946  mov     ebx, eax
0x180543948  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18054394d  test    ebx, ebx
0x18054394f  jnz     loc_1805439FC
0x180543955  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054395b  lea     rcx, [rax+38h]; Parameter
0x18054395f  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180543964  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054396a  mov     rcx, rdi; pszPath
0x18054396d  lea     rbx, [rax+108h]
0x180543974  call    cs:__imp_PathGetDriveNumberW
0x18054397a  xor     r8d, r8d; struct CMtPtRemote *
0x18054397d  mov     rcx, rbx; this
0x180543980  mov     edx, eax; int
0x180543982  call    ?SetRemote@CDriveLetterCache@@QEAAXHPEAVCMtPtRemote@@@Z; CDriveLetterCache::SetRemote(int,CMtPtRemote *)
0x180543987  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054398d  lea     rcx, [rax+38h]; lpCriticalSection
0x180543991  call    cs:__imp_LeaveCriticalSection
0x180543997  xor     r9d, r9d; dwItem2
0x18054399a  mov     r8, rdi; dwItem1
0x18054399d  lea     ebx, [r9+5]
0x1805439a1  mov     edx, ebx; uFlags
0x1805439a3  lea     ecx, [rbx+7Bh]; wEventId
0x1805439a6  call    cs:__imp_SHChangeNotify
0x1805439ac  lea     r8, [rsp+58h+var_28]
0x1805439b1  mov     [rsp+58h+var_28], 0
0x1805439ba  xor     edx, edx
0x1805439bc  mov     rcx, rdi
0x1805439bf  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x1805439c4  test    eax, eax
0x1805439c6  js      short loc_1805439FC
0x1805439c8  mov     rcx, rdi; unsigned __int16 *
0x1805439cb  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x1805439d0  test    eax, eax
0x1805439d2  jz      short loc_1805439DF
0x1805439d4  mov     rdx, rdi; unsigned __int16 *
0x1805439d7  lea     ecx, [rbx-4]; int
0x1805439da  call    ?CDBurn_OnDeviceChange@@YAJHPEBG@Z; CDBurn_OnDeviceChange(int,ushort const *)
0x1805439df  xor     r9d, r9d; dwItem2
0x1805439e2  mov     r8, rdi; dwItem1
0x1805439e5  mov     edx, ebx; uFlags
0x1805439e7  mov     ecx, 100h; wEventId
0x1805439ec  call    cs:__imp_SHChangeNotify
0x1805439f2  mov     rcx, [rsp+58h+var_28]; this
0x1805439f7  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1805439fc  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180543a03  jz      short loc_180543A21
0x180543a05  lea     rax, [rsp+58h+var_28]
0x180543a0a  mov     r9d, 1
0x180543a10  lea     rdx, Shell32_MountPoint_WMDeviceChange_NetShareRemoval_Stop
0x180543a17  mov     [rsp+58h+var_38], rax
0x180543a1c  call    McGenEventWrite_EventWriteTransfer
0x180543a21  mov     rcx, [rsp+58h+var_18]
0x180543a26  xor     rcx, rsp; StackCookie
0x180543a29  call    __security_check_cookie
0x180543a2e  mov     rbx, [rsp+58h+arg_8]
0x180543a33  mov     rsi, [rsp+58h+arg_10]
0x180543a38  add     rsp, 50h
0x180543a3c  pop     rdi
0x180543a3d  retn
```
