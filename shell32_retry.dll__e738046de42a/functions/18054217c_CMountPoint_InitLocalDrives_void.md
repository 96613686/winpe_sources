# CMountPoint::_InitLocalDrives(void)

- ea: `0x18054217c`
- end: `0x180542359`
- name: `?_InitLocalDrives@CMountPoint@@CAJXZ`
- size: `477`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800bfc60`
- `0x180541a0c`

## callees

- `0x18008cad4`
- `0x1801d13c0`
- `0x180233280`
- `0x18054142c`
- `0x180541f74`
- `0x18054217c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180542308`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180542308`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1805422e9`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1805422e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180542266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180542266`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180542256`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180542256`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180542226`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180542226`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18054223c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18054223c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1805421bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180542287`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1805421bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180542287`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805422ff`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1805422ff`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054219a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805421af`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542270`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054228f`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805422a4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805422da`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054232e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054219a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805421af`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180542270`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054228f`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805422a4`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805422da`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18054232e`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1805421f0`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1805421f0`

## pseudocode

```c
__int64 CMountPoint::_InitLocalDrives(void)
{
  signed int inited; // edi
  __int64 v1; // rcx
  __int64 v2; // r8
  int v3; // ebx
  HANDLE Thread; // rax
  void *v5; // rbx
  int v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD TickCount; // ebx
  DWORD LogicalDrives; // esi
  unsigned int i; // ebx
  const WCHAR *v12; // rax
  UINT DriveTypeW; // eax
  DWORD ExitCode; // [rsp+30h] [rbp-48h] BYREF
  DWORD ThreadId[4]; // [rsp+38h] [rbp-40h] BYREF

  inited = -2147467259;
  if ( *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1120) )
  {
    v3 = *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1120);
    if ( GetTickCount() - v3 <= 0x1388 )
      goto LABEL_29;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v1, &Shell32_MountPoint_InitLocalDrives_Start, v2, 1, ThreadId);
  if ( (unsigned int)IsDesktopExplorerProcess() )
  {
    ThreadId[0] = 0;
    Thread = CreateThread(0, 0, FirstHardwareEnumThreadProc, 0, 0, ThreadId);
    v5 = Thread;
    if ( !Thread )
      goto LABEL_12;
    if ( WaitForSingleObject(Thread, 0xFFFFFFFF) != -1 )
    {
      ExitCode = 0;
      if ( GetExitCodeThread(v5, &ExitCode) )
        inited = ExitCode;
    }
    CloseHandle(v5);
    if ( inited >= 0 )
    {
      *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1120) = 0;
      CMountPoint::RegisterForHardwareNotifications(v6);
    }
    else
    {
LABEL_12:
      TickCount = GetTickCount();
      *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1120) = TickCount;
    }
  }
  else
  {
    inited = CMountPoint::_InitLocalDriveHelper();
    *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1120) = 0;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, &Shell32_MountPoint_InitLocalDrives_Stop, v8, 1, ThreadId);
  if ( inited < 0 )
  {
LABEL_29:
    if ( *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1116) )
    {
      return 1;
    }
    else
    {
      LogicalDrives = GetLogicalDrives();
      for ( i = 0; i < 0x1A; ++i )
      {
        if ( _bittest((const int *)&LogicalDrives, i) )
        {
          v12 = PathBuildRootW((LPWSTR)ThreadId, i);
          DriveTypeW = GetDriveTypeW(v12);
          if ( (DriveTypeW & 0xFFFFFFFA) != 0 || DriveTypeW == 5 )
            inited = CMtPtLocal::_CreateMtPtLocal((const unsigned __int16 *)ThreadId);
        }
      }
      *(_DWORD *)(Global_WindowsStorage_Untyped_MountPoint() + 1116) = 1;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18054217c  push    rbx
0x18054217e  push    rsi
0x18054217f  push    rdi
0x180542180  push    r14
0x180542182  sub     rsp, 58h
0x180542186  mov     rax, cs:__security_cookie
0x18054218d  xor     rax, rsp
0x180542190  mov     [rsp+78h+var_30], rax
0x180542195  mov     edi, 80004005h
0x18054219a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805421a0  mov     r14d, 1
0x1805421a6  cmp     dword ptr [rax+460h], 0
0x1805421ad  jz      short loc_1805421CE
0x1805421af  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805421b5  mov     ebx, [rax+460h]
0x1805421bb  call    cs:__imp_GetTickCount
0x1805421c1  sub     eax, ebx
0x1805421c3  cmp     eax, 1388h
0x1805421c8  jbe     loc_1805422DA
0x1805421ce  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x1805421d5  jz      short loc_1805421F0
0x1805421d7  lea     rax, [rsp+78h+ThreadId]
0x1805421dc  mov     r9d, r14d
0x1805421df  lea     rdx, Shell32_MountPoint_InitLocalDrives_Start
0x1805421e6  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x1805421eb  call    McGenEventWrite_EventWriteTransfer
0x1805421f0  call    cs:__imp_IsDesktopExplorerProcess
0x1805421f6  test    eax, eax
0x1805421f8  jz      loc_18054229D
0x1805421fe  lea     rax, [rsp+78h+ThreadId]
0x180542203  mov     [rsp+78h+ThreadId], 0
0x18054220b  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180542210  lea     r8, ?FirstHardwareEnumThreadProc@@YAKPEAX@Z; lpStartAddress
0x180542217  xor     r9d, r9d; lpParameter
0x18054221a  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180542222  xor     edx, edx; dwStackSize
0x180542224  xor     ecx, ecx; lpThreadAttributes
0x180542226  call    cs:__imp_CreateThread
0x18054222c  mov     rbx, rax
0x18054222f  test    rax, rax
0x180542232  jz      short loc_180542287
0x180542234  or      esi, 0FFFFFFFFh
0x180542237  mov     rcx, rax; hHandle
0x18054223a  mov     edx, esi; dwMilliseconds
0x18054223c  call    cs:__imp_WaitForSingleObject
0x180542242  cmp     eax, esi
0x180542244  jz      short loc_180542263
0x180542246  lea     rdx, [rsp+78h+ExitCode]; lpExitCode
0x18054224b  mov     [rsp+78h+ExitCode], 0
0x180542253  mov     rcx, rbx; hThread
0x180542256  call    cs:__imp_GetExitCodeThread
0x18054225c  test    eax, eax
0x18054225e  cmovnz  edi, [rsp+78h+ExitCode]
0x180542263  mov     rcx, rbx; hObject
0x180542266  call    cs:__imp_CloseHandle
0x18054226c  test    edi, edi
0x18054226e  js      short loc_180542287
0x180542270  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542276  mov     dword ptr [rax+460h], 0
0x180542280  call    ?RegisterForHardwareNotifications@CMountPoint@@SAJH@Z; CMountPoint::RegisterForHardwareNotifications(int)
0x180542285  jmp     short loc_1805422B4
0x180542287  call    cs:__imp_GetTickCount
0x18054228d  mov     ebx, eax
0x18054228f  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542295  mov     [rax+460h], ebx
0x18054229b  jmp     short loc_1805422B4
0x18054229d  call    ?_InitLocalDriveHelper@CMountPoint@@SAJXZ; CMountPoint::_InitLocalDriveHelper(void)
0x1805422a2  mov     edi, eax
0x1805422a4  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805422aa  mov     dword ptr [rax+460h], 0
0x1805422b4  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x1805422bb  jz      short loc_1805422D6
0x1805422bd  lea     rax, [rsp+78h+ThreadId]
0x1805422c2  mov     r9d, r14d
0x1805422c5  lea     rdx, Shell32_MountPoint_InitLocalDrives_Stop
0x1805422cc  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x1805422d1  call    McGenEventWrite_EventWriteTransfer
0x1805422d6  test    edi, edi
0x1805422d8  jns     short loc_180542340
0x1805422da  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805422e0  cmp     dword ptr [rax+45Ch], 0
0x1805422e7  jnz     short loc_18054233D
0x1805422e9  call    cs:__imp_GetLogicalDrives
0x1805422ef  mov     esi, eax
0x1805422f1  xor     ebx, ebx
0x1805422f3  bt      esi, ebx
0x1805422f6  jnb     short loc_180542326
0x1805422f8  mov     edx, ebx; iDrive
0x1805422fa  lea     rcx, [rsp+78h+ThreadId]; pszRoot
0x1805422ff  call    cs:__imp_PathBuildRootW
0x180542305  mov     rcx, rax; lpRootPathName
0x180542308  call    cs:__imp_GetDriveTypeW
0x18054230e  test    eax, 0FFFFFFFAh
0x180542313  jnz     short loc_18054231A
0x180542315  cmp     eax, 5
0x180542318  jnz     short loc_180542326
0x18054231a  lea     rcx, [rsp+78h+ThreadId]; unsigned __int16 *
0x18054231f  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x180542324  mov     edi, eax
0x180542326  add     ebx, r14d
0x180542329  cmp     ebx, 1Ah
0x18054232c  jb      short loc_1805422F3
0x18054232e  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180542334  mov     [rax+45Ch], r14d
0x18054233b  jmp     short loc_180542340
0x18054233d  mov     edi, r14d
0x180542340  mov     eax, edi
0x180542342  mov     rcx, [rsp+78h+var_30]
0x180542347  xor     rcx, rsp; StackCookie
0x18054234a  call    __security_check_cookie
0x18054234f  add     rsp, 58h
0x180542353  pop     r14
0x180542355  pop     rdi
0x180542356  pop     rsi
0x180542357  pop     rbx
0x180542358  retn
```
