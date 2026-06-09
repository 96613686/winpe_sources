# CMountPoint::HandleMountPointLocalEventThreadProc(void *)

- ea: `0x1805820e0`
- end: `0x180582325`
- name: `?HandleMountPointLocalEventThreadProc@CMountPoint@@SAKPEAX@Z`
- size: `581`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180016364`
- `0x18001a2bc`
- `0x18001aa98`
- `0x18009a6d8`
- `0x18009b938`
- `0x1800dbe2c`
- `0x18012f0b8`
- `0x1801e80a4`
- `0x180249490`
- `0x1805820e0`
- `0x1805823bc`
- `0x18058265c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805822f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805822f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805821ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1805821ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180582293`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180582134`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180582221`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180582134`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180582221`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18058216d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582258`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18058216d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180582258`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1805821d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1805822bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1805821d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1805822bb`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582142`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582157`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058219b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058222d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582242`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582283`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582142`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582157`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058219b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058222d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582242`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180582283`

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
  void *v14; // rdx
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
      McGenEventWrite_EventWriteTransfer(Parameter, &Shell32_MountPoint_WMDeviceChange_MediaArrival_Start, a3, 1, v22);
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
      v14 = &Shell32_MountPoint_WMDeviceChange_MediaArrival_Stop;
LABEL_24:
      McGenEventWrite_EventWriteTransfer(v11, v14, v12, 1, v22);
    }
  }
  else
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        Parameter,
        &Shell32_MountPoint_WMDeviceChange_MountPointArrival_Start,
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
      v14 = &Shell32_MountPoint_WMDeviceChange_MountPointArrival_Stop;
      goto LABEL_24;
    }
  }
  LocalFree(Parameter);
  return 0;
}

```

## disassembly

```asm
0x1805820e0  mov     r11, rsp
0x1805820e3  mov     [r11+10h], rbx
0x1805820e7  mov     [r11+18h], rbp
0x1805820eb  push    rsi
0x1805820ec  sub     rsp, 50h
0x1805820f0  mov     rax, cs:__security_cookie
0x1805820f7  xor     rax, rsp
0x1805820fa  mov     [rsp+58h+var_18], rax
0x1805820ff  cmp     dword ptr [rcx+8], 0
0x180582103  mov     rsi, rcx
0x180582106  jz      loc_1805821F7
0x18058210c  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180582113  jz      short loc_18058212F
0x180582115  lea     rax, [r11-28h]
0x180582119  mov     r9d, 1
0x18058211f  lea     rdx, Shell32_MountPoint_WMDeviceChange_MediaArrival_Start
0x180582126  mov     [r11-38h], rax
0x18058212a  call    McGenEventWrite_EventWriteTransfer
0x18058212f  mov     ecx, 0BB8h; dwMilliseconds
0x180582134  call    cs:__imp_Sleep
0x18058213b  nop     dword ptr [rax+rax+00h]
0x180582140  xor     ebp, ebp
0x180582142  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582149  nop     dword ptr [rax+rax+00h]
0x18058214e  lea     rcx, [rax+38h]; Parameter
0x180582152  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180582157  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18058215e  nop     dword ptr [rax+rax+00h]
0x180582163  mov     rcx, rsi; pszPath
0x180582166  lea     rbx, [rax+108h]
0x18058216d  call    cs:__imp_PathGetDriveNumberW
0x180582174  nop     dword ptr [rax+rax+00h]
0x180582179  mov     edx, eax; int
0x18058217b  mov     rcx, rbx; this
0x18058217e  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x180582183  mov     rcx, rax; this
0x180582186  test    rax, rax
0x180582189  jz      short loc_18058219B
0x18058218b  call    ?CanUseVolume@CMtPtLocal@@QEBAHXZ; CMtPtLocal::CanUseVolume(void)
0x180582190  test    eax, eax
0x180582192  setz    bpl
0x180582196  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18058219b  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805821a2  nop     dword ptr [rax+rax+00h]
0x1805821a7  lea     rcx, [rax+38h]; lpCriticalSection
0x1805821ab  call    cs:__imp_LeaveCriticalSection
0x1805821b2  nop     dword ptr [rax+rax+00h]
0x1805821b7  test    ebp, ebp
0x1805821b9  jz      short loc_1805821DE
0x1805821bb  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1805821c0  mov     ebx, eax
0x1805821c2  test    eax, eax
0x1805821c4  js      short loc_1805821CE
0x1805821c6  mov     rcx, rsi; unsigned __int16 *
0x1805821c9  call    ?OnMediaArrival@CMountPoint@@SAXPEBG@Z; CMountPoint::OnMediaArrival(ushort const *)
0x1805821ce  test    ebx, ebx
0x1805821d0  jnz     short loc_1805821DE
0x1805821d2  call    cs:__imp_CoUninitialize
0x1805821d9  nop     dword ptr [rax+rax+00h]
0x1805821de  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1805821e5  jz      loc_1805822F6
0x1805821eb  lea     rdx, Shell32_MountPoint_WMDeviceChange_MediaArrival_Stop
0x1805821f2  jmp     loc_1805822E1
0x1805821f7  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1805821fe  jz      short loc_18058221C
0x180582200  lea     rax, [rsp+58h+var_28]
0x180582205  mov     r9d, 1
0x18058220b  lea     rdx, Shell32_MountPoint_WMDeviceChange_MountPointArrival_Start
0x180582212  mov     [rsp+58h+var_38], rax
0x180582217  call    McGenEventWrite_EventWriteTransfer
0x18058221c  mov     ecx, 0BB8h; dwMilliseconds
0x180582221  call    cs:__imp_Sleep
0x180582228  nop     dword ptr [rax+rax+00h]
0x18058222d  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582234  nop     dword ptr [rax+rax+00h]
0x180582239  lea     rcx, [rax+38h]; Parameter
0x18058223d  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x180582242  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180582249  nop     dword ptr [rax+rax+00h]
0x18058224e  mov     rcx, rsi; pszPath
0x180582251  lea     rbx, [rax+108h]
0x180582258  call    cs:__imp_PathGetDriveNumberW
0x18058225f  nop     dword ptr [rax+rax+00h]
0x180582264  mov     edx, eax; int
0x180582266  mov     rcx, rbx; this
0x180582269  call    ?GetLocal@CDriveLetterCache@@QEAAPEAVCMtPtLocal@@H@Z; CDriveLetterCache::GetLocal(int)
0x18058226e  mov     [rsp+58h+var_28], rax
0x180582273  mov     rbx, rax
0x180582276  test    rax, rax
0x180582279  jnz     short loc_180582283
0x18058227b  mov     rcx, rsi; unsigned __int16 *
0x18058227e  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x180582283  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18058228a  nop     dword ptr [rax+rax+00h]
0x18058228f  lea     rcx, [rax+38h]; lpCriticalSection
0x180582293  call    cs:__imp_LeaveCriticalSection
0x18058229a  nop     dword ptr [rax+rax+00h]
0x18058229f  test    rbx, rbx
0x1805822a2  jnz     short loc_1805822C7
0x1805822a4  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1805822a9  mov     ebx, eax
0x1805822ab  test    eax, eax
0x1805822ad  js      short loc_1805822B7
0x1805822af  mov     rcx, rsi; unsigned __int16 *
0x1805822b2  call    ?OnMountPointArrival@CMountPoint@@SAXPEBG@Z; CMountPoint::OnMountPointArrival(ushort const *)
0x1805822b7  test    ebx, ebx
0x1805822b9  jnz     short loc_1805822C7
0x1805822bb  call    cs:__imp_CoUninitialize
0x1805822c2  nop     dword ptr [rax+rax+00h]
0x1805822c7  lea     rcx, [rsp+58h+var_28]
0x1805822cc  call    ??$SafeRelease@VCMtPtRemote@@@@YAXPEAPEAVCMtPtRemote@@@Z; SafeRelease<CMtPtRemote>(CMtPtRemote * *)
0x1805822d1  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1805822d8  jz      short loc_1805822F6
0x1805822da  lea     rdx, Shell32_MountPoint_WMDeviceChange_MountPointArrival_Stop
0x1805822e1  lea     rax, [rsp+58h+var_28]
0x1805822e6  mov     r9d, 1
0x1805822ec  mov     [rsp+58h+var_38], rax
0x1805822f1  call    McGenEventWrite_EventWriteTransfer
0x1805822f6  mov     rcx, rsi; hMem
0x1805822f9  call    cs:__imp_LocalFree
0x180582300  nop     dword ptr [rax+rax+00h]
0x180582305  xor     eax, eax
0x180582307  mov     rcx, [rsp+58h+var_18]
0x18058230c  xor     rcx, rsp; StackCookie
0x18058230f  call    __security_check_cookie
0x180582314  mov     rbx, [rsp+58h+arg_8]
0x180582319  mov     rbp, [rsp+58h+arg_10]
0x18058231e  add     rsp, 50h
0x180582322  pop     rsi
0x180582323  retn
```
