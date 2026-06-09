# CMountPoint::OnMediaRemoval(ushort const *)

- ea: `0x180582448`
- end: `0x180582655`
- name: `?OnMediaRemoval@CMountPoint@@SAXPEBG@Z`
- size: `525`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update`

## callers

- `0x180581edc`
- `0x1805835c8`

## callees

- `0x18001a064`
- `0x18001a2bc`
- `0x18001a2fc`
- `0x18001aa98`
- `0x18009a838`
- `0x1800b32d4`
- `0x180185cbc`
- `0x180249490`
- `0x180258644`
- `0x1802657a8`
- `0x180303440`
- `0x1805817ac`
- `0x180582448`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180582557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180582557`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180582480`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180582480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058257c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18058257c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582598`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180582543`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180582543`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1805824de`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1805824de`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18058250c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18058250c`
- `USER32!GetForegroundWindow` at `0x1805824b2`
- `USER32!GetForegroundWindow` at `0x1805824b2`
- `USER32!GetWindowThreadProcessId` at `0x1805824c6`
- `USER32!GetWindowThreadProcessId` at `0x1805824c6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582495`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805824f6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582588`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582495`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805824f6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582588`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805825d9`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x1805825d9`

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
0x180582448  push    rbp
0x18058244a  push    rbx
0x18058244b  push    rsi
0x18058244c  push    rdi
0x18058244d  lea     rbp, [rsp-158h]
0x180582455  sub     rsp, 258h
0x18058245c  mov     rax, cs:__security_cookie
0x180582463  xor     rax, rsp
0x180582466  mov     [rbp+170h+var_30], rax
0x18058246d  mov     rdi, rcx
0x180582470  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x180582475  test    eax, eax
0x180582477  jz      loc_1805825A4
0x18058247d  mov     rcx, rdi; lpRootPathName
0x180582480  call    cs:__imp_GetDriveTypeW
0x180582487  nop     dword ptr [rax+rax+00h]
0x18058248c  cmp     eax, 5
0x18058248f  jnz     loc_1805825A4
0x180582495  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18058249c  nop     dword ptr [rax+rax+00h]
0x1805824a1  lea     rcx, [rax+38h]; Parameter
0x1805824a5  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1805824aa  mov     [rsp+270h+dwProcessId], 0
0x1805824b2  call    cs:__imp_GetForegroundWindow
0x1805824b9  nop     dword ptr [rax+rax+00h]
0x1805824be  mov     rcx, rax; hWnd
0x1805824c1  lea     rdx, [rsp+270h+dwProcessId]; lpdwProcessId
0x1805824c6  call    cs:__imp_GetWindowThreadProcessId
0x1805824cd  nop     dword ptr [rax+rax+00h]
0x1805824d2  mov     r8d, [rsp+270h+dwProcessId]; dwProcessId
0x1805824d7  xor     edx, edx; bInheritHandle
0x1805824d9  mov     ecx, 1000h; dwDesiredAccess
0x1805824de  call    cs:__imp_OpenProcess
0x1805824e5  nop     dword ptr [rax+rax+00h]
0x1805824ea  mov     rsi, rax
0x1805824ed  test    rax, rax
0x1805824f0  jz      loc_180582588
0x1805824f6  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805824fd  nop     dword ptr [rax+rax+00h]
0x180582502  mov     rcx, rdi; pszPath
0x180582505  lea     rbx, [rax+108h]
0x18058250c  call    cs:__imp_PathGetDriveNumberW
0x180582513  nop     dword ptr [rax+rax+00h]
0x180582518  mov     edx, eax; int
0x18058251a  mov     rcx, rbx; this
0x18058251d  call    ?GetDriveLetterData@CDriveLetterCache@@QEAAPEAVCDriveLetterData@@H@Z; CDriveLetterCache::GetDriveLetterData(int)
0x180582522  mov     ecx, [rsp+270h+dwProcessId]
0x180582526  lea     r9, [rsp+270h+dwSize]; lpdwSize
0x18058252b  lea     r8, [rsp+270h+ExeName]; lpExeName
0x180582530  xor     edx, edx; dwFlags
0x180582532  mov     rbx, rax
0x180582535  mov     [rax+14h], ecx
0x180582538  mov     rcx, rsi; hProcess
0x18058253b  mov     [rsp+270h+dwSize], 104h
0x180582543  call    cs:__imp_QueryFullProcessImageNameW
0x18058254a  nop     dword ptr [rax+rax+00h]
0x18058254f  test    eax, eax
0x180582551  jz      short loc_180582579
0x180582553  mov     rcx, [rbx+18h]; hMem
0x180582557  call    cs:__imp_LocalFree
0x18058255e  nop     dword ptr [rax+rax+00h]
0x180582563  lea     r9, [rbx+18h]
0x180582567  mov     qword ptr [rbx+18h], 0
0x18058256f  lea     r8, [rsp+270h+ExeName]
0x180582574  call    ??$_AllocString@VCTLocalAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTLocalAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180582579  mov     rcx, rsi; hObject
0x18058257c  call    cs:__imp_CloseHandle
0x180582583  nop     dword ptr [rax+rax+00h]
0x180582588  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18058258f  nop     dword ptr [rax+rax+00h]
0x180582594  lea     rcx, [rax+38h]; lpCriticalSection
0x180582598  call    cs:__imp_LeaveCriticalSection
0x18058259f  nop     dword ptr [rax+rax+00h]
0x1805825a4  xor     edx, edx
0x1805825a6  mov     rcx, rdi
0x1805825a9  call    ?_LocalDriveIsCoveredByNetDrive@CMountPoint@@CA_NPEBGW4AddToDriveLetterCache@@@Z; CMountPoint::_LocalDriveIsCoveredByNetDrive(ushort const *,AddToDriveLetterCache)
0x1805825ae  test    al, al
0x1805825b0  jnz     loc_180582639
0x1805825b6  mov     rcx, rdi; unsigned __int16 *
0x1805825b9  call    ?IsDriveLetter@CMountPoint@@SAHPEBG@Z; CMountPoint::IsDriveLetter(ushort const *)
0x1805825be  test    eax, eax
0x1805825c0  jz      short loc_1805825CC
0x1805825c2  mov     rdx, rdi; unsigned __int16 *
0x1805825c5  xor     ecx, ecx; int
0x1805825c7  call    ?CDBurn_OnMediaChange@@YAJHPEBG@Z; CDBurn_OnMediaChange(int,ushort const *)
0x1805825cc  xor     r9d, r9d; dwItem2
0x1805825cf  mov     r8, rdi; dwItem1
0x1805825d2  lea     edx, [r9+5]; uFlags
0x1805825d6  lea     ecx, [rdx+3Bh]; wEventId
0x1805825d9  call    cs:__imp_SHChangeNotify
0x1805825e0  nop     dword ptr [rax+rax+00h]
0x1805825e5  call    ?NotifyDeviceUpdateLocations@CMountPoint@@KAJJ@Z; CMountPoint::NotifyDeviceUpdateLocations(long)
0x1805825ea  call    IsSHELL32_SHIsVirtualDevicePresent
0x1805825ef  test    al, al
0x1805825f1  jz      short loc_1805825FB
0x1805825f3  mov     rcx, rdi; lpString2
0x1805825f6  call    SHELL32_CloseAutoplayPrompt
0x1805825fb  lea     r8, [rsp+270h+dwSize]
0x180582600  mov     qword ptr [rsp+270h+dwSize], 0
0x180582609  xor     edx, edx
0x18058260b  mov     rcx, rdi
0x18058260e  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x180582613  test    eax, eax
0x180582615  js      short loc_180582639
0x180582617  mov     rcx, qword ptr [rsp+270h+dwSize]
0x18058261c  lea     rdx, pszBagName; "Shell"
0x180582623  mov     rax, [rcx]
0x180582626  mov     rax, [rax+20h]
0x18058262a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18058262f  mov     rcx, qword ptr [rsp+270h+dwSize]; this
0x180582634  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x180582639  mov     rcx, [rbp+170h+var_30]
0x180582640  xor     rcx, rsp; StackCookie
0x180582643  call    __security_check_cookie
0x180582648  add     rsp, 258h
0x18058264f  pop     rdi
0x180582650  pop     rsi
0x180582651  pop     rbx
0x180582652  pop     rbp
0x180582653  retn
```
