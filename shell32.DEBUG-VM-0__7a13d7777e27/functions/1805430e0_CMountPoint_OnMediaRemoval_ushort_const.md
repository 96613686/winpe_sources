# CMountPoint::OnMediaRemoval(ushort const *)

- ea: `0x1805430e0`
- end: `0x180543296`
- name: `?OnMediaRemoval@CMountPoint@@SAXPEBG@Z`
- size: `438`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update`

## callers

- `0x180542c14`
- `0x180544088`

## callees

- `0x180019c34`
- `0x1800bf924`
- `0x1800bfb48`
- `0x1800bfb80`
- `0x1800c0204`
- `0x1800c0c44`
- `0x180174198`
- `0x180233280`
- `0x1802423f4`
- `0x18024eb54`
- `0x1802e4a60`
- `0x18054253c`
- `0x1805430e0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805431bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805431bb`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180543118`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180543118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805431da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805431da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805431ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805431ea`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1805431ad`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1805431ad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18054315e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18054315e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18054317c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18054317c`
- `USER32!GetForegroundWindow` at `0x18054313e`
- `USER32!GetForegroundWindow` at `0x18054313e`
- `USER32!GetWindowThreadProcessId` at `0x18054314c`
- `USER32!GetWindowThreadProcessId` at `0x18054314c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543127`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054316c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805431e0`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180543127`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054316c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805431e0`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180543221`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x180543221`

## pseudocode

```c
void __fastcall CMountPoint::OnMediaRemoval(const unsigned __int16 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  HWND ForegroundWindow; // rax
  __int64 v5; // rcx
  HANDLE v6; // rsi
  CDriveLetterCache *v7; // rbx
  int DriveNumberW; // eax
  struct CDriveLetterData *DriveLetterData; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  DWORD dwProcessId; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize[2]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR ExeName[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( (unsigned int)CMountPoint::IsDriveLetter(a1) && GetDriveTypeW(a1) == 5 )
  {
    v3 = Global_WindowsStorage_Untyped_MountPoint(v2);
    CCritSecDelayInitBase::Enter((PVOID)(v3 + 56));
    dwProcessId = 0;
    ForegroundWindow = GetForegroundWindow();
    GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
    v6 = OpenProcess(0x1000u, 0, dwProcessId);
    if ( v6 )
    {
      v7 = (CDriveLetterCache *)(Global_WindowsStorage_Untyped_MountPoint(v5) + 264);
      DriveNumberW = PathGetDriveNumberW(a1);
      DriveLetterData = CDriveLetterCache::GetDriveLetterData(v7, DriveNumberW);
      *((_DWORD *)DriveLetterData + 5) = dwProcessId;
      dwSize[0] = 260;
      if ( QueryFullProcessImageNameW(v6, 0, ExeName, dwSize) )
      {
        LocalFree(*((HLOCAL *)DriveLetterData + 3));
        *((_QWORD *)DriveLetterData + 3) = 0;
        _AllocString<CTLocalAllocPolicy>(v11, v10, ExeName, (char *)DriveLetterData + 24);
      }
      CloseHandle(v6);
    }
    v12 = Global_WindowsStorage_Untyped_MountPoint(v5);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 56));
  }
  if ( !(unsigned __int8)CMountPoint::_LocalDriveIsCoveredByNetDrive(a1, 0) )
  {
    if ( (unsigned int)CMountPoint::IsDriveLetter(a1) )
      CDBurn_OnMediaChange(0, a1);
    SHChangeNotify(64, 5u, a1, 0);
    CMountPoint::NotifyDeviceUpdateLocations(v13);
    if ( (unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent() )
      SHELL32_CloseAutoplayPrompt(a1);
    *(_QWORD *)dwSize = 0;
    if ( (int)CMountPoint::GetMountPoint(a1, 0, (struct CMountPoint **)dwSize) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, const WCHAR *))(**(_QWORD **)dwSize + 32LL))(*(_QWORD *)dwSize, L"Shell");
      CMountPoint::Release(*(CMountPoint **)dwSize);
    }
  }
}

```

## disassembly

```asm
0x1805430e0  push    rbp
0x1805430e2  push    rbx
0x1805430e3  push    rsi
0x1805430e4  push    rdi
0x1805430e5  lea     rbp, [rsp-158h]
0x1805430ed  sub     rsp, 258h
0x1805430f4  mov     rax, cs:__security_cookie
0x1805430fb  xor     rax, rsp
0x1805430fe  mov     [rbp+170h+var_30], rax
0x180543105  mov     rdi, rcx
0x180543108  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x18054310d  test    eax, eax
0x18054310f  jz      loc_1805431F0
0x180543115  mov     rcx, rdi; lpRootPathName
0x180543118  call    cs:__imp_GetDriveTypeW
0x18054311e  cmp     eax, 5
0x180543121  jnz     loc_1805431F0
0x180543127  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18054312d  lea     rcx, [rax+38h]; Parameter
0x180543131  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180543136  mov     [rsp+270h+dwProcessId], 0
0x18054313e  call    cs:__imp_GetForegroundWindow
0x180543144  mov     rcx, rax; hWnd
0x180543147  lea     rdx, [rsp+270h+dwProcessId]; lpdwProcessId
0x18054314c  call    cs:__imp_GetWindowThreadProcessId
0x180543152  mov     r8d, [rsp+270h+dwProcessId]; dwProcessId
0x180543157  xor     edx, edx; bInheritHandle
0x180543159  mov     ecx, 1000h; dwDesiredAccess
0x18054315e  call    cs:__imp_OpenProcess
0x180543164  mov     rsi, rax
0x180543167  test    rax, rax
0x18054316a  jz      short loc_1805431E0
0x18054316c  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180543172  mov     rcx, rdi; pszPath
0x180543175  lea     rbx, [rax+108h]
0x18054317c  call    cs:__imp_PathGetDriveNumberW
0x180543182  mov     edx, eax; int
0x180543184  mov     rcx, rbx; this
0x180543187  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x18054318c  mov     ecx, [rsp+270h+dwProcessId]
0x180543190  lea     r9, [rsp+270h+dwSize]; lpdwSize
0x180543195  lea     r8, [rsp+270h+ExeName]; lpExeName
0x18054319a  xor     edx, edx; dwFlags
0x18054319c  mov     rbx, rax
0x18054319f  mov     [rax+14h], ecx
0x1805431a2  mov     rcx, rsi; hProcess
0x1805431a5  mov     [rsp+270h+dwSize], 104h
0x1805431ad  call    cs:__imp_QueryFullProcessImageNameW
0x1805431b3  test    eax, eax
0x1805431b5  jz      short loc_1805431D7
0x1805431b7  mov     rcx, [rbx+18h]; hMem
0x1805431bb  call    cs:__imp_LocalFree
0x1805431c1  lea     r9, [rbx+18h]
0x1805431c5  mov     qword ptr [rbx+18h], 0
0x1805431cd  lea     r8, [rsp+270h+ExeName]
0x1805431d2  call    ??$_AllocString@VCTLocalAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTLocalAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1805431d7  mov     rcx, rsi; hObject
0x1805431da  call    cs:__imp_CloseHandle
0x1805431e0  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805431e6  lea     rcx, [rax+38h]; lpCriticalSection
0x1805431ea  call    cs:__imp_LeaveCriticalSection
0x1805431f0  xor     edx, edx
0x1805431f2  mov     rcx, rdi
0x1805431f5  call    ?_LocalDriveIsCoveredByNetDrive@CMountPoint@@CA_NPEBGW4AddToDriveLetterCache@@@Z; CMountPoint::_LocalDriveIsCoveredByNetDrive(ushort const *,AddToDriveLetterCache)
0x1805431fa  test    al, al
0x1805431fc  jnz     short loc_18054327B
0x1805431fe  mov     rcx, rdi; unsigned __int16 *
0x180543201  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x180543206  test    eax, eax
0x180543208  jz      short loc_180543214
0x18054320a  mov     rdx, rdi; unsigned __int16 *
0x18054320d  xor     ecx, ecx; int
0x18054320f  call    ?CDBurn_OnMediaChange@@YAJHPEBG@Z; CDBurn_OnMediaChange(int,ushort const *)
0x180543214  xor     r9d, r9d; dwItem2
0x180543217  mov     r8, rdi; dwItem1
0x18054321a  lea     edx, [r9+5]; uFlags
0x18054321e  lea     ecx, [rdx+3Bh]; wEventId
0x180543221  call    cs:__imp_SHChangeNotify
0x180543227  call    ?NotifyDeviceUpdateLocations@CMountPoint@@KAJJ@Z; CMountPoint::NotifyDeviceUpdateLocations(long)
0x18054322c  call    IsSHELL32_SHIsVirtualDevicePresent
0x180543231  test    al, al
0x180543233  jz      short loc_18054323D
0x180543235  mov     rcx, rdi; lpString2
0x180543238  call    SHELL32_CloseAutoplayPrompt
0x18054323d  lea     r8, [rsp+270h+dwSize]
0x180543242  mov     qword ptr [rsp+270h+dwSize], 0
0x18054324b  xor     edx, edx
0x18054324d  mov     rcx, rdi
0x180543250  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x180543255  test    eax, eax
0x180543257  js      short loc_18054327B
0x180543259  mov     rcx, qword ptr [rsp+270h+dwSize]
0x18054325e  lea     rdx, pszBagName; "Shell"
0x180543265  mov     rax, [rcx]
0x180543268  mov     rax, [rax+20h]
0x18054326c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180543271  mov     rcx, qword ptr [rsp+270h+dwSize]; this
0x180543276  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18054327b  mov     rcx, [rbp+170h+var_30]
0x180543282  xor     rcx, rsp; StackCookie
0x180543285  call    __security_check_cookie
0x18054328a  add     rsp, 258h
0x180543291  pop     rdi
0x180543292  pop     rsi
0x180543293  pop     rbx
0x180543294  pop     rbp
0x180543295  retn
```
