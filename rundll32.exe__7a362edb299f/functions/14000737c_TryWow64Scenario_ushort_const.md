# _TryWow64Scenario(ushort const *)

- ea: `0x14000737c`
- end: `0x1400076b0`
- name: `?_TryWow64Scenario@@YAHPEBG@Z`
- size: `820`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006e44`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x14000737c`

## import_xrefs

- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14000741d`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14000741d`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x140007473`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x140007473`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400075ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400075ff`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400075a7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400075a7`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14000751a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14000754a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14000751a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14000754a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000762a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000764c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140007676`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000762a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x14000764c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x140007676`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400075e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400075e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000740a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000740a`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140007582`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x140007582`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140007527`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140007527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007635`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007681`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007635`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007681`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400074a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400074a3`
- `api-ms-win-core-wow64-l1-1-0!Wow64EnableWow64FsRedirection` at `0x1400074d1`
- `api-ms-win-core-wow64-l1-1-0!Wow64EnableWow64FsRedirection` at `0x1400075ed`
- `api-ms-win-core-wow64-l1-1-0!Wow64EnableWow64FsRedirection` at `0x1400074d1`
- `api-ms-win-core-wow64-l1-1-0!Wow64EnableWow64FsRedirection` at `0x1400075ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000760c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000760c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007616`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400074c1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400074c1`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x14000744d`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x14000744d`
- `ntdll!RtlGetImageFileMachines` at `0x1400073c4`
- `ntdll!RtlGetImageFileMachines` at `0x1400073c4`

## string_xrefs

- `0x1400074b1`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall _TryWow64Scenario(const unsigned __int16 *a1)
{
  unsigned __int16 v1; // bx
  HANDLE CurrentProcess; // rax
  UINT SystemDirectoryW; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v4; // rcx
  WCHAR *CommandLineW; // rax
  BOOL v6; // ebx
  DWORD v7; // ebx
  _BYTE v9[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v10; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v11; // [rsp+58h] [rbp-A8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+60h] [rbp-A0h]
  unsigned __int16 Value; // [rsp+68h] [rbp-98h] BYREF
  ULONG_PTR Size; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST v17; // [rsp+F8h] [rbp-8h]
  WCHAR Buffer[264]; // [rsp+100h] [rbp+0h] BYREF

  v9[0] = 0;
  v10 = 0;
  v11 = 0;
  LODWORD(Size) = 0;
  if ( (int)RtlGetImageFileMachines(a1, &Size) < 0 )
    return 0;
  if ( (Size & 8) != 0 )
  {
    v1 = -21916;
  }
  else if ( (Size & 2) != 0 )
  {
    v1 = -31132;
  }
  else if ( (Size & 1) != 0 )
  {
    v1 = 332;
  }
  else
  {
    if ( (Size & 0x10) == 0 )
      return 0;
    v1 = -31132;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v10, &v11) )
    return 0;
  if ( v1 == v11 || v11 == -21916 && (v1 == 0x8664 || v1 == 0xAA64) )
  {
    if ( !v10 && (v11 != -21916 || v1 != 0x8664 && v1 != 0xAA64) )
      return 0;
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0xF6u);
  }
  else
  {
    if ( (int)RtlWow64IsWowGuestMachineSupported(v1, v9) < 0 || !v9[0] )
      return 0;
    SystemDirectoryW = GetSystemWow64Directory2W(Buffer, 246, v1);
  }
  if ( !SystemDirectoryW || PathCchAppend(Buffer, 0x105u, L"rundll32.exe") < 0 )
    return 0;
  Wow64EnableWow64FsRedirection(0);
  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  StartupInfo.cb = 112;
  lpAttributeList = 0;
  Value = 0;
  if ( v10 != v1 )
  {
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    lpAttributeList = (LPPROC_THREAD_ATTRIBUTE_LIST)LocalAlloc(0, Size);
    v4 = lpAttributeList;
    if ( lpAttributeList )
    {
      if ( InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size) )
      {
        Value = v1;
        if ( UpdateProcThreadAttribute(lpAttributeList, 0, 0x20019u, &Value, 2u, 0, 0) )
        {
          v17 = lpAttributeList;
          goto LABEL_30;
        }
      }
      v4 = lpAttributeList;
    }
    if ( v4 )
    {
      DeleteProcThreadAttributeList(v4);
      LocalFree(lpAttributeList);
      v4 = 0;
      lpAttributeList = 0;
    }
    Value = 0;
    goto LABEL_40;
  }
LABEL_30:
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  CommandLineW = GetCommandLineW();
  v6 = CreateProcessW(Buffer, CommandLineW, 0, 0, 0, 0x80000u, 0, 0, &StartupInfo, &ProcessInformation);
  Wow64EnableWow64FsRedirection(1u);
  if ( !v6
    || (v7 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF),
        CloseHandle(ProcessInformation.hProcess),
        CloseHandle(ProcessInformation.hThread),
        v7) )
  {
    v4 = lpAttributeList;
LABEL_40:
    if ( v4 )
    {
      DeleteProcThreadAttributeList(v4);
      LocalFree(lpAttributeList);
    }
    return 0;
  }
  if ( lpAttributeList )
  {
    DeleteProcThreadAttributeList(lpAttributeList);
    LocalFree(lpAttributeList);
  }
  return 1;
}

```

## disassembly

```asm
0x14000737c  mov     [rsp-8+arg_8], rbx
0x140007381  mov     [rsp-8+arg_10], rsi
0x140007386  push    rbp
0x140007387  push    rdi
0x140007388  push    r14
0x14000738a  lea     rbp, [rsp-220h]
0x140007392  sub     rsp, 320h
0x140007399  mov     rax, cs:__security_cookie
0x1400073a0  xor     rax, rsp
0x1400073a3  mov     [rbp+230h+var_20], rax
0x1400073aa  xor     edi, edi
0x1400073ac  lea     rdx, [rsp+330h+Size]
0x1400073b1  mov     [rsp+330h+var_2E0], dil
0x1400073b6  mov     [rsp+330h+var_2DC], di
0x1400073bb  mov     [rsp+330h+var_2D8], di
0x1400073c0  mov     dword ptr [rsp+330h+Size], edi
0x1400073c4  call    cs:__imp_RtlGetImageFileMachines
0x1400073ca  test    eax, eax
0x1400073cc  js      loc_140007687
0x1400073d2  mov     eax, dword ptr [rsp+330h+Size]
0x1400073d6  mov     esi, 0AA64h
0x1400073db  mov     r14d, 8664h
0x1400073e1  test    al, 8
0x1400073e3  jz      short loc_1400073EA
0x1400073e5  movzx   ebx, si
0x1400073e8  jmp     short loc_14000740A
0x1400073ea  test    al, 2
0x1400073ec  jz      short loc_1400073F3
0x1400073ee  mov     ebx, r14d
0x1400073f1  jmp     short loc_14000740A
0x1400073f3  test    al, 1
0x1400073f5  jz      short loc_1400073FE
0x1400073f7  mov     ebx, 14Ch
0x1400073fc  jmp     short loc_14000740A
0x1400073fe  test    al, 10h
0x140007400  jz      loc_140007687
0x140007406  movzx   ebx, r14w
0x14000740a  call    cs:__imp_GetCurrentProcess
0x140007410  mov     rcx, rax
0x140007413  lea     r8, [rsp+330h+var_2D8]
0x140007418  lea     rdx, [rsp+330h+var_2DC]
0x14000741d  call    cs:__imp_IsWow64Process2
0x140007423  test    eax, eax
0x140007425  jz      loc_140007687
0x14000742b  movzx   eax, [rsp+330h+var_2D8]
0x140007430  cmp     bx, ax
0x140007433  jz      short loc_14000747B
0x140007435  cmp     ax, si
0x140007438  jnz     short loc_140007445
0x14000743a  cmp     bx, r14w
0x14000743e  jz      short loc_14000747B
0x140007440  cmp     bx, si
0x140007443  jz      short loc_14000747B
0x140007445  lea     rdx, [rsp+330h+var_2E0]
0x14000744a  movzx   ecx, bx
0x14000744d  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x140007453  test    eax, eax
0x140007455  js      loc_140007687
0x14000745b  cmp     [rsp+330h+var_2E0], dil
0x140007460  jz      loc_140007687
0x140007466  movzx   r8d, bx
0x14000746a  lea     rcx, [rbp+230h+Buffer]
0x14000746e  mov     edx, 0F6h
0x140007473  call    cs:__imp_GetSystemWow64Directory2W
0x140007479  jmp     short loc_1400074A9
0x14000747b  cmp     [rsp+330h+var_2DC], di
0x140007480  jnz     short loc_14000749A
0x140007482  cmp     ax, si
0x140007485  jnz     loc_140007687
0x14000748b  cmp     bx, r14w
0x14000748f  jz      short loc_14000749A
0x140007491  cmp     bx, si
0x140007494  jnz     loc_140007687
0x14000749a  mov     edx, 0F6h; uSize
0x14000749f  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x1400074a3  call    cs:__imp_GetSystemDirectoryW
0x1400074a9  test    eax, eax
0x1400074ab  jz      loc_140007687
0x1400074b1  lea     r8, pszMore; "rundll32.exe"
0x1400074b8  mov     edx, 105h; cchPath
0x1400074bd  lea     rcx, [rbp+230h+Buffer]; pszPath
0x1400074c1  call    cs:__imp_PathCchAppend
0x1400074c7  test    eax, eax
0x1400074c9  js      loc_140007687
0x1400074cf  xor     ecx, ecx; Wow64FsEnableRedirection
0x1400074d1  call    cs:__imp_Wow64EnableWow64FsRedirection
0x1400074d7  xor     eax, eax
0x1400074d9  lea     rcx, [rbp+230h+StartupInfo.lpReserved]; void *
0x1400074dd  xor     edx, edx; Val
0x1400074df  mov     dword ptr [rbp+230h+StartupInfo+4], eax
0x1400074e2  lea     r8d, [rax+68h]; Size
0x1400074e6  call    memset_0
0x1400074eb  mov     [rbp+230h+StartupInfo.cb], 70h ; 'p'
0x1400074f2  mov     [rsp+330h+lpAttributeList], rdi
0x1400074f7  mov     [rsp+330h+Value], di
0x1400074fc  cmp     [rsp+330h+var_2DC], bx
0x140007501  jz      loc_140007599
0x140007507  xor     r8d, r8d; dwFlags
0x14000750a  mov     [rsp+330h+Size], rdi
0x14000750f  lea     r9, [rsp+330h+Size]; lpSize
0x140007514  xor     ecx, ecx; lpAttributeList
0x140007516  lea     edx, [r8+1]; dwAttributeCount
0x14000751a  call    cs:__imp_InitializeProcThreadAttributeList
0x140007520  mov     rdx, [rsp+330h+Size]; uBytes
0x140007525  xor     ecx, ecx; uFlags
0x140007527  call    cs:__imp_LocalAlloc
0x14000752d  mov     [rsp+330h+lpAttributeList], rax
0x140007532  mov     rcx, rax; lpAttributeList
0x140007535  test    rax, rax
0x140007538  jz      loc_140007647
0x14000753e  xor     r8d, r8d; dwFlags
0x140007541  lea     r9, [rsp+330h+Size]; lpSize
0x140007546  lea     edx, [r8+1]; dwAttributeCount
0x14000754a  call    cs:__imp_InitializeProcThreadAttributeList
0x140007550  test    eax, eax
0x140007552  jz      loc_140007642
0x140007558  mov     rcx, [rsp+330h+lpAttributeList]; lpAttributeList
0x14000755d  lea     r9, [rsp+330h+Value]; lpValue
0x140007562  mov     [rsp+330h+lpReturnSize], rdi; lpReturnSize
0x140007567  xor     edx, edx; dwFlags
0x140007569  mov     [rsp+330h+lpPreviousValue], rdi; lpPreviousValue
0x14000756e  mov     r8d, 20019h; Attribute
0x140007574  mov     [rsp+330h+cbSize], 2; cbSize
0x14000757d  mov     [rsp+330h+Value], bx
0x140007582  call    cs:__imp_UpdateProcThreadAttribute
0x140007588  test    eax, eax
0x14000758a  jz      loc_140007642
0x140007590  mov     rax, [rsp+330h+lpAttributeList]
0x140007595  mov     [rbp+230h+var_238], rax
0x140007599  xorps   xmm0, xmm0
0x14000759c  xor     eax, eax
0x14000759e  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x1400075a3  mov     qword ptr [rbp+230h+ProcessInformation.dwProcessId], rax
0x1400075a7  call    cs:__imp_GetCommandLineW
0x1400075ad  xor     r9d, r9d; lpThreadAttributes
0x1400075b0  lea     rcx, [rbp+230h+Buffer]; lpApplicationName
0x1400075b4  mov     rdx, rax; lpCommandLine
0x1400075b7  xor     r8d, r8d; lpProcessAttributes
0x1400075ba  lea     rax, [rsp+330h+ProcessInformation]
0x1400075bf  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x1400075c4  lea     rax, [rbp+230h+StartupInfo]
0x1400075c8  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x1400075cd  mov     [rsp+330h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x1400075d2  mov     [rsp+330h+lpReturnSize], rdi; lpEnvironment
0x1400075d7  mov     dword ptr [rsp+330h+lpPreviousValue], 80000h; dwCreationFlags
0x1400075df  mov     dword ptr [rsp+330h+cbSize], edi; bInheritHandles
0x1400075e3  call    cs:__imp_CreateProcessW
0x1400075e9  mov     cl, 1; Wow64FsEnableRedirection
0x1400075eb  mov     ebx, eax
0x1400075ed  call    cs:__imp_Wow64EnableWow64FsRedirection
0x1400075f3  test    ebx, ebx
0x1400075f5  jz      short loc_14000766C
0x1400075f7  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hHandle
0x1400075fc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400075ff  call    cs:__imp_WaitForSingleObject
0x140007605  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x14000760a  mov     ebx, eax
0x14000760c  call    cs:__imp_CloseHandle
0x140007612  mov     rcx, [rbp+230h+ProcessInformation.hThread]; hObject
0x140007616  call    cs:__imp_CloseHandle
0x14000761c  test    ebx, ebx
0x14000761e  jnz     short loc_14000766C
0x140007620  mov     rcx, [rsp+330h+lpAttributeList]; lpAttributeList
0x140007625  test    rcx, rcx
0x140007628  jz      short loc_14000763B
0x14000762a  call    cs:__imp_DeleteProcThreadAttributeList
0x140007630  mov     rcx, [rsp+330h+lpAttributeList]; hMem
0x140007635  call    cs:__imp_LocalFree
0x14000763b  mov     eax, 1
0x140007640  jmp     short loc_140007689
0x140007642  mov     rcx, [rsp+330h+lpAttributeList]; lpAttributeList
0x140007647  test    rcx, rcx
0x14000764a  jz      short loc_140007665
0x14000764c  call    cs:__imp_DeleteProcThreadAttributeList
0x140007652  mov     rcx, [rsp+330h+lpAttributeList]; hMem
0x140007657  call    cs:__imp_LocalFree
0x14000765d  mov     rcx, rdi
0x140007660  mov     [rsp+330h+lpAttributeList], rcx
0x140007665  mov     [rsp+330h+Value], di
0x14000766a  jmp     short loc_140007671
0x14000766c  mov     rcx, [rsp+330h+lpAttributeList]; lpAttributeList
0x140007671  test    rcx, rcx
0x140007674  jz      short loc_140007687
0x140007676  call    cs:__imp_DeleteProcThreadAttributeList
0x14000767c  mov     rcx, [rsp+330h+lpAttributeList]; hMem
0x140007681  call    cs:__imp_LocalFree
0x140007687  xor     eax, eax
0x140007689  mov     rcx, [rbp+230h+var_20]
0x140007690  xor     rcx, rsp; StackCookie
0x140007693  call    __security_check_cookie
0x140007698  lea     r11, [rsp+330h+var_10]
0x1400076a0  mov     rbx, [r11+28h]
0x1400076a4  mov     rsi, [r11+30h]
0x1400076a8  mov     rsp, r11
0x1400076ab  pop     r14
0x1400076ad  pop     rdi
0x1400076ae  pop     rbp
0x1400076af  retn
```
