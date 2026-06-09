# CMountPoint::_InitLocalDrives(void)

- ea: `0x18058133c`
- end: `0x180581584`
- name: `?_InitLocalDrives@CMountPoint@@CAJXZ`
- size: `584`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001a3e4`
- `0x180580a70`

## callees

- `0x1800dbe2c`
- `0x1801e80a4`
- `0x180249490`
- `0x180580394`
- `0x1805810d4`
- `0x18058133c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180581526`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180581526`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1805814fb`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1805814fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180581450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180581450`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1805813fe`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1805813fe`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18058143a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18058143a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18058141a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18058141a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180581387`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18058147d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180581387`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18058147d`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180581517`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180581517`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058135a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581375`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581460`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058148b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805814a6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805814e6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581552`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058135a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581375`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581460`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x18058148b`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805814a6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x1805814e6`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_Untyped_MountPoint` at `0x180581552`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1805813c2`
- `Windows.Storage!IsDesktopExplorerProcess` at `0x1805813c2`

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
0x18058133c  push    rbx
0x18058133e  push    rsi
0x18058133f  push    rdi
0x180581340  push    r14
0x180581342  sub     rsp, 58h
0x180581346  mov     rax, cs:__security_cookie
0x18058134d  xor     rax, rsp
0x180581350  mov     [rsp+78h+var_30], rax
0x180581355  mov     edi, 80004005h
0x18058135a  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180581361  nop     dword ptr [rax+rax+00h]
0x180581366  mov     r14d, 1
0x18058136c  cmp     dword ptr [rax+460h], 0
0x180581373  jz      short loc_1805813A0
0x180581375  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x18058137c  nop     dword ptr [rax+rax+00h]
0x180581381  mov     ebx, [rax+460h]
0x180581387  call    cs:__imp_GetTickCount
0x18058138e  nop     dword ptr [rax+rax+00h]
0x180581393  sub     eax, ebx
0x180581395  cmp     eax, 1388h
0x18058139a  jbe     loc_1805814E6
0x1805813a0  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x1805813a7  jz      short loc_1805813C2
0x1805813a9  lea     rax, [rsp+78h+ThreadId]
0x1805813ae  mov     r9d, r14d
0x1805813b1  lea     rdx, Shell32_MountPoint_InitLocalDrives_Start
0x1805813b8  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x1805813bd  call    McGenEventWrite_EventWriteTransfer
0x1805813c2  call    cs:__imp_IsDesktopExplorerProcess
0x1805813c9  nop     dword ptr [rax+rax+00h]
0x1805813ce  test    eax, eax
0x1805813d0  jz      loc_18058149F
0x1805813d6  lea     rax, [rsp+78h+ThreadId]
0x1805813db  mov     [rsp+78h+ThreadId], 0
0x1805813e3  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x1805813e8  lea     r8, ?FirstHardwareEnumThreadProc@@YAKPEAX@Z; lpStartAddress
0x1805813ef  xor     r9d, r9d; lpParameter
0x1805813f2  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1805813fa  xor     edx, edx; dwStackSize
0x1805813fc  xor     ecx, ecx; lpThreadAttributes
0x1805813fe  call    cs:__imp_CreateThread
0x180581405  nop     dword ptr [rax+rax+00h]
0x18058140a  mov     rbx, rax
0x18058140d  test    rax, rax
0x180581410  jz      short loc_18058147D
0x180581412  or      esi, 0FFFFFFFFh
0x180581415  mov     rcx, rax; hHandle
0x180581418  mov     edx, esi; dwMilliseconds
0x18058141a  call    cs:__imp_WaitForSingleObject
0x180581421  nop     dword ptr [rax+rax+00h]
0x180581426  cmp     eax, esi
0x180581428  jz      short loc_18058144D
0x18058142a  lea     rdx, [rsp+78h+ExitCode]; lpExitCode
0x18058142f  mov     [rsp+78h+ExitCode], 0
0x180581437  mov     rcx, rbx; hThread
0x18058143a  call    cs:__imp_GetExitCodeThread
0x180581441  nop     dword ptr [rax+rax+00h]
0x180581446  test    eax, eax
0x180581448  cmovnz  edi, [rsp+78h+ExitCode]
0x18058144d  mov     rcx, rbx; hObject
0x180581450  call    cs:__imp_CloseHandle
0x180581457  nop     dword ptr [rax+rax+00h]
0x18058145c  test    edi, edi
0x18058145e  js      short loc_18058147D
0x180581460  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180581467  nop     dword ptr [rax+rax+00h]
0x18058146c  mov     dword ptr [rax+460h], 0
0x180581476  call    ?RegisterForHardwareNotifications@CMountPoint@@SAJH@Z; CMountPoint::RegisterForHardwareNotifications(int)
0x18058147b  jmp     short loc_1805814BC
0x18058147d  call    cs:__imp_GetTickCount
0x180581484  nop     dword ptr [rax+rax+00h]
0x180581489  mov     ebx, eax
0x18058148b  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180581492  nop     dword ptr [rax+rax+00h]
0x180581497  mov     [rax+460h], ebx
0x18058149d  jmp     short loc_1805814BC
0x18058149f  call    ?_InitLocalDriveHelper@CMountPoint@@SAJXZ; CMountPoint::_InitLocalDriveHelper(void)
0x1805814a4  mov     edi, eax
0x1805814a6  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805814ad  nop     dword ptr [rax+rax+00h]
0x1805814b2  mov     dword ptr [rax+460h], 0
0x1805814bc  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, r14b
0x1805814c3  jz      short loc_1805814DE
0x1805814c5  lea     rax, [rsp+78h+ThreadId]
0x1805814ca  mov     r9d, r14d
0x1805814cd  lea     rdx, Shell32_MountPoint_InitLocalDrives_Stop
0x1805814d4  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x1805814d9  call    McGenEventWrite_EventWriteTransfer
0x1805814de  test    edi, edi
0x1805814e0  jns     loc_18058156A
0x1805814e6  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x1805814ed  nop     dword ptr [rax+rax+00h]
0x1805814f2  cmp     dword ptr [rax+45Ch], 0
0x1805814f9  jnz     short loc_180581567
0x1805814fb  call    cs:__imp_GetLogicalDrives
0x180581502  nop     dword ptr [rax+rax+00h]
0x180581507  mov     esi, eax
0x180581509  xor     ebx, ebx
0x18058150b  bt      esi, ebx
0x18058150e  jnb     short loc_18058154A
0x180581510  mov     edx, ebx; iDrive
0x180581512  lea     rcx, [rsp+78h+ThreadId]; pszRoot
0x180581517  call    cs:__imp_PathBuildRootW
0x18058151e  nop     dword ptr [rax+rax+00h]
0x180581523  mov     rcx, rax; lpRootPathName
0x180581526  call    cs:__imp_GetDriveTypeW
0x18058152d  nop     dword ptr [rax+rax+00h]
0x180581532  test    eax, 0FFFFFFFAh
0x180581537  jnz     short loc_18058153E
0x180581539  cmp     eax, 5
0x18058153c  jnz     short loc_18058154A
0x18058153e  lea     rcx, [rsp+78h+ThreadId]; unsigned __int16 *
0x180581543  call    ?_CreateMtPtLocal@CMtPtLocal@@CAJPEBG@Z; CMtPtLocal::_CreateMtPtLocal(ushort const *)
0x180581548  mov     edi, eax
0x18058154a  add     ebx, r14d
0x18058154d  cmp     ebx, 1Ah
0x180581550  jb      short loc_18058150B
0x180581552  call    cs:__imp_Global_WindowsStorage_Untyped_MountPoint
0x180581559  nop     dword ptr [rax+rax+00h]
0x18058155e  mov     [rax+45Ch], r14d
0x180581565  jmp     short loc_18058156A
0x180581567  mov     edi, r14d
0x18058156a  mov     eax, edi
0x18058156c  mov     rcx, [rsp+78h+var_30]
0x180581571  xor     rcx, rsp; StackCookie
0x180581574  call    __security_check_cookie
0x180581579  add     rsp, 58h
0x18058157d  pop     r14
0x18058157f  pop     rdi
0x180581580  pop     rsi
0x180581581  pop     rbx
0x180581582  retn
```
