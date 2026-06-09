# CMountPoint::HandleMountPointLocalEventThreadProc(void *)

- ea: `0x180542de0`
- end: `0x180542fca`
- name: `?HandleMountPointLocalEventThreadProc@CMountPoint@@SAKPEAX@Z`
- size: `490`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18001df70`
- `0x18008cad4`
- `0x1800be5c0`
- `0x1800bfb48`
- `0x1800c0204`
- `0x1800c0d3c`
- `0x1800c0e68`
- `0x1801d13c0`
- `0x180233280`
- `0x180542de0`
- `0x180543060`
- `0x18054329c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180542fa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180542fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180542e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180542f4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180542e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180542f4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180542e34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180542ef7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180542e34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180542ef7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180542e5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180542f1c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180542e5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180542f1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180542eae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180542f6d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180542eae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180542f6d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e3c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e4b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e83`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542efd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542f0c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542f41`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e3c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e4b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542e83`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542efd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542f0c`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542f41`

## pseudocode

```c
__int64 __fastcall CMountPoint::HandleMountPointLocalEventThreadProc(WCHAR *Parameter, __int64 a2, __int64 a3)
{
  int v4; // ebp
  __int64 v5; // rax
  CDriveLetterCache *v6; // rbx
  int DriveNumberW; // eax
  CMtPtLocal *Local; // rcx
  CMountPoint *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ebx
  __int64 *v14; // rdx
  __int64 v15; // rax
  CDriveLetterCache *v16; // rbx
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  int v20; // ebx
  _QWORD v22[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)Parameter + 2) )
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(Parameter, Shell32_MountPoint_WMDeviceChange_MediaArrival_Start, a3, 1, v22);
    Sleep(0xBB8u);
    v4 = 0;
    v5 = ((__int64 (*)(void))Global_WindowsStorage_Untyped_MountPoint)();
    CCritSecDelayInitBase::Enter((PVOID)(v5 + 56));
    v6 = (CDriveLetterCache *)(((__int64 (*)(void))Global_WindowsStorage_Untyped_MountPoint)() + 264);
    DriveNumberW = PathGetDriveNumberW(Parameter);
    Local = CDriveLetterCache::GetLocal(v6, DriveNumberW);
    if ( Local )
    {
      LOBYTE(v4) = (unsigned int)CMtPtLocal::CanUseVolume(Local) == 0;
      CMountPoint::Release(v9);
    }
    v10 = Global_WindowsStorage_Untyped_MountPoint(Local);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 56));
    if ( v4 )
    {
      v13 = SHCoInitialize();
      if ( v13 >= 0 )
        CMountPoint::OnMediaArrival(Parameter);
      if ( !v13 )
        CoUninitialize();
    }
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    {
      v14 = Shell32_MountPoint_WMDeviceChange_MediaArrival_Stop;
LABEL_24:
      McGenEventWrite_EventWriteTransfer(v11, v14, v12, 1, v22);
    }
  }
  else
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Parameter,
        Shell32_MountPoint_WMDeviceChange_MountPointArrival_Start,
        a3,
        1,
        v22);
    Sleep(0xBB8u);
    v15 = ((__int64 (*)(void))Global_WindowsStorage_Untyped_MountPoint)();
    CCritSecDelayInitBase::Enter((PVOID)(v15 + 56));
    v16 = (CDriveLetterCache *)(((__int64 (*)(void))Global_WindowsStorage_Untyped_MountPoint)() + 264);
    v17 = PathGetDriveNumberW(Parameter);
    v22[0] = CDriveLetterCache::GetLocal(v16, v17);
    v18 = v22[0];
    if ( !v22[0] )
      CMtPtLocal::_CreateMtPtLocal(Parameter);
    v19 = ((__int64 (*)(void))Global_WindowsStorage_Untyped_MountPoint)();
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 56));
    if ( !v18 )
    {
      v20 = SHCoInitialize();
      if ( v20 >= 0 )
        CMountPoint::OnMountPointArrival(Parameter);
      if ( !v20 )
        CoUninitialize();
    }
    SafeRelease<CMtPtRemote>(v22);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    {
      v14 = Shell32_MountPoint_WMDeviceChange_MountPointArrival_Stop;
      goto LABEL_24;
    }
  }
  LocalFree(Parameter);
  return 0;
}

```

## disassembly

```asm
0x180542de0  mov     r11, rsp
0x180542de3  mov     [r11+10h], rbx
0x180542de7  mov     [r11+18h], rbp
0x180542deb  push    rsi
0x180542dec  sub     rsp, 50h
0x180542df0  mov     rax, cs:__security_cookie
0x180542df7  xor     rax, rsp
0x180542dfa  mov     [rsp+58h+var_18], rax
0x180542dff  cmp     dword ptr [rcx+8], 0
0x180542e03  mov     rsi, rcx
0x180542e06  jz      loc_180542ECD
0x180542e0c  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180542e13  jz      short loc_180542E2F
0x180542e15  lea     rax, [r11-28h]
0x180542e19  mov     r9d, 1
0x180542e1f  lea     rdx, Shell32_MountPoint_WMDeviceChange_MediaArrival_Start
0x180542e26  mov     [r11-38h], rax
0x180542e2a  call    McGenEventWrite_EventWriteTransfer
0x180542e2f  mov     ecx, 0BB8h; dwMilliseconds
0x180542e34  call    cs:__imp_Sleep
0x180542e3a  xor     ebp, ebp
0x180542e3c  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542e42  lea     rcx, [rax+38h]; Parameter
0x180542e46  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180542e4b  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542e51  mov     rcx, rsi; pszPath
0x180542e54  lea     rbx, [rax+108h]
0x180542e5b  call    cs:__imp_PathGetDriveNumberW
0x180542e61  mov     edx, eax; int
0x180542e63  mov     rcx, rbx; this
0x180542e66  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x180542e6b  mov     rcx, rax; this
0x180542e6e  test    rax, rax
0x180542e71  jz      short loc_180542E83
0x180542e73  call    ?CanUseVolume@CMtPtLocal@@QEBAHXZ; CMtPtLocal::CanUseVolume(void)
0x180542e78  test    eax, eax
0x180542e7a  setz    bpl
0x180542e7e  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x180542e83  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542e89  lea     rcx, [rax+38h]; lpCriticalSection
0x180542e8d  call    cs:__imp_LeaveCriticalSection
0x180542e93  test    ebp, ebp
0x180542e95  jz      short loc_180542EB4
0x180542e97  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180542e9c  mov     ebx, eax
0x180542e9e  test    eax, eax
0x180542ea0  js      short loc_180542EAA
0x180542ea2  mov     rcx, rsi; unsigned __int16 *
0x180542ea5  call    ?OnMediaArrival@CMountPoint@@SAXPEBG@Z; CMountPoint::OnMediaArrival(ushort const *)
0x180542eaa  test    ebx, ebx
0x180542eac  jnz     short loc_180542EB4
0x180542eae  call    cs:__imp_CoUninitialize
0x180542eb4  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180542ebb  jz      loc_180542FA2
0x180542ec1  lea     rdx, Shell32_MountPoint_WMDeviceChange_MediaArrival_Stop
0x180542ec8  jmp     loc_180542F8D
0x180542ecd  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180542ed4  jz      short loc_180542EF2
0x180542ed6  lea     rax, [rsp+58h+var_28]
0x180542edb  mov     r9d, 1
0x180542ee1  lea     rdx, Shell32_MountPoint_WMDeviceChange_MountPointArrival_Start
0x180542ee8  mov     [rsp+58h+var_38], rax
0x180542eed  call    McGenEventWrite_EventWriteTransfer
0x180542ef2  mov     ecx, 0BB8h; dwMilliseconds
0x180542ef7  call    cs:__imp_Sleep
0x180542efd  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542f03  lea     rcx, [rax+38h]; Parameter
0x180542f07  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180542f0c  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542f12  mov     rcx, rsi; pszPath
0x180542f15  lea     rbx, [rax+108h]
0x180542f1c  call    cs:__imp_PathGetDriveNumberW
0x180542f22  mov     edx, eax; int
0x180542f24  mov     rcx, rbx; this
0x180542f27  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x180542f2c  mov     [rsp+58h+var_28], rax
0x180542f31  mov     rbx, rax
0x180542f34  test    rax, rax
0x180542f37  jnz     short loc_180542F41
0x180542f39  mov     rcx, rsi; unsigned __int16 *
0x180542f3c  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x180542f41  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542f47  lea     rcx, [rax+38h]; lpCriticalSection
0x180542f4b  call    cs:__imp_LeaveCriticalSection
0x180542f51  test    rbx, rbx
0x180542f54  jnz     short loc_180542F73
0x180542f56  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180542f5b  mov     ebx, eax
0x180542f5d  test    eax, eax
0x180542f5f  js      short loc_180542F69
0x180542f61  mov     rcx, rsi; unsigned __int16 *
0x180542f64  call    ?OnMountPointArrival@CMountPoint@@SAXPEBG@Z; CMountPoint::OnMountPointArrival(ushort const *)
0x180542f69  test    ebx, ebx
0x180542f6b  jnz     short loc_180542F73
0x180542f6d  call    cs:__imp_CoUninitialize
0x180542f73  lea     rcx, [rsp+58h+var_28]
0x180542f78  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x180542f7d  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180542f84  jz      short loc_180542FA2
0x180542f86  lea     rdx, Shell32_MountPoint_WMDeviceChange_MountPointArrival_Stop
0x180542f8d  lea     rax, [rsp+58h+var_28]
0x180542f92  mov     r9d, 1
0x180542f98  mov     [rsp+58h+var_38], rax
0x180542f9d  call    McGenEventWrite_EventWriteTransfer
0x180542fa2  mov     rcx, rsi; hMem
0x180542fa5  call    cs:__imp_LocalFree
0x180542fab  xor     eax, eax
0x180542fad  mov     rcx, [rsp+58h+var_18]
0x180542fb2  xor     rcx, rsp; StackCookie
0x180542fb5  call    __security_check_cookie
0x180542fba  mov     rbx, [rsp+58h+arg_8]
0x180542fbf  mov     rbp, [rsp+58h+arg_10]
0x180542fc4  add     rsp, 50h
0x180542fc8  pop     rsi
0x180542fc9  retn
```
