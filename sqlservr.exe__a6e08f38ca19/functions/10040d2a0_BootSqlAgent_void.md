# BootSqlAgent(void)

- ea: `0x10040d2a0`
- end: `0x10040d5c4`
- name: `?BootSqlAgent@@YAXXZ`
- size: `804`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100412470`

## callees

- `0x100401580`
- `0x100404a30`
- `0x10040d2a0`
- `0x10041eac0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x10040d30a`
- `KERNEL32!GetModuleFileNameW` at `0x10040d30a`
- `KERNEL32!CreateProcessW` at `0x10040d498`
- `KERNEL32!CreateProcessW` at `0x10040d498`
- `KERNEL32!RegisterWaitForSingleObject` at `0x10040d52e`
- `KERNEL32!RegisterWaitForSingleObject` at `0x10040d52e`
- `KERNEL32!GetLastError` at `0x10040d4a2`
- `KERNEL32!GetLastError` at `0x10040d538`
- `KERNEL32!GetLastError` at `0x10040d4a2`
- `KERNEL32!GetLastError` at `0x10040d538`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d358`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d3e5`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d4c0`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d556`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d358`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d3e5`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d4c0`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10040d556`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d35e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d3eb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d4c6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d55c`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d35e`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d3eb`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d4c6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10040d55c`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10040d349`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x10040d349`

## string_xrefs

- `0x10040d3a6`: `SqlAgent\SqlAgent.exe`
- `0x10040d364`: `Failed to _wsplitpath_s.`
- `0x10040d3fc`: `Failed to launch sql agent.`
- `0x10040d4d7`: `Failed to launch sqlagent.`
- `0x10040d43a`: `sqlagent.exe -c -xdb`
- `0x10040d56d`: `Failed to register sql agent exit callback.`

## pseudocode

```c
void BootSqlAgent(void)
{
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v1; // eax
  char *v2; // rcx
  signed int v3; // eax
  signed int v4; // ebx
  struct __crt_locale_pointers *v5; // rax
  int v6; // eax
  char *v7; // rcx
  signed int LastError; // eax
  int v9; // ebx
  struct __crt_locale_pointers *v10; // rax
  int v11; // eax
  char *v12; // rcx
  signed int v13; // eax
  int v14; // ebx
  struct __crt_locale_pointers *v15; // rax
  int v16; // eax
  char *v17; // rcx
  DWORD dwCreationFlags[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwCreationFlagsa[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwCreationFlagsb[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwCreationFlagsc[2]; // [rsp+28h] [rbp-D8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE phNewWaitObject; // [rsp+68h] [rbp-98h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Drive; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR CommandLine[28]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Filename[264]; // [rsp+120h] [rbp+20h] BYREF
  char Buffer[512]; // [rsp+330h] [rbp+230h] BYREF
  char v29[512]; // [rsp+530h] [rbp+430h] BYREF
  char v30[512]; // [rsp+730h] [rbp+630h] BYREF
  char v31[512]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t Dir[264]; // [rsp+B30h] [rbp+A30h] BYREF
  WCHAR ApplicationName[264]; // [rsp+D40h] [rbp+C40h] BYREF

  StartupInfo.cb = 104;
  memset(&StartupInfo.cb + 1, 0, 100);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  GetModuleFileNameW(0, Filename, 0x104u);
  Filename[259] = 0;
  if ( _wsplitpath_s(Filename, &Drive, 4u, Dir, 0x101u, 0, 0, 0, 0) )
  {
    SetWin32ExitCode(0x80070057);
    DefaultLocale = GetDefaultLocale();
    dwCreationFlags[0] = -2147024809;
    v1 = StringCchPrintf_lA(
           Buffer,
           0x200u,
           "%hs (HRESULT 0x%x)",
           DefaultLocale,
           "Failed to _wsplitpath_s.",
           *(_QWORD *)dwCreationFlags);
    v2 = "Failed to _wsplitpath_s.";
    if ( v1 >= 0 )
      v2 = Buffer;
    FailAndExit(v2);
  }
  v3 = StringCchPrintfW(ApplicationName, 0x104u, L"%s%s%s", &Drive, Dir, L"SqlAgent\\SqlAgent.exe");
  v4 = v3;
  if ( v3 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v3);
    v5 = GetDefaultLocale();
    dwCreationFlagsa[0] = v4;
    v6 = StringCchPrintf_lA(
           v29,
           0x200u,
           "%hs (HRESULT 0x%x)",
           v5,
           "Failed to launch sql agent.",
           *(_QWORD *)dwCreationFlagsa);
    v7 = "Failed to launch sql agent.";
    if ( v6 >= 0 )
      v7 = v29;
    FailAndExit(v7);
  }
  wcscpy(CommandLine, L"sqlagent.exe -c -xdb");
  if ( !CreateProcessW(ApplicationName, CommandLine, 0, 0, 0, 0x8010000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v9);
      v10 = GetDefaultLocale();
      dwCreationFlagsb[0] = v9;
      v11 = StringCchPrintf_lA(
              v30,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v10,
              "Failed to launch sqlagent.",
              *(_QWORD *)dwCreationFlagsb);
      v12 = "Failed to launch sqlagent.";
      if ( v11 >= 0 )
        v12 = v30;
      FailAndExit(v12);
    }
  }
  if ( !RegisterWaitForSingleObject(
          &phNewWaitObject,
          ProcessInformation.hProcess,
          SqlAgentProcessExitCallback,
          0,
          0xFFFFFFFF,
          8u) )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v14 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v14);
      v15 = GetDefaultLocale();
      dwCreationFlagsc[0] = v14;
      v16 = StringCchPrintf_lA(
              v31,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v15,
              "Failed to register sql agent exit callback.",
              *(_QWORD *)dwCreationFlagsc);
      v17 = "Failed to register sql agent exit callback.";
      if ( v16 >= 0 )
        v17 = v31;
      FailAndExit(v17);
    }
  }
}

```

## disassembly

```asm
0x10040d2a0  mov     [rsp-8+arg_0], rbx
0x10040d2a5  mov     [rsp-8+arg_8], rdi
0x10040d2aa  push    rbp
0x10040d2ab  lea     rbp, [rsp-0E60h]
0x10040d2b3  sub     rsp, 0F60h
0x10040d2ba  mov     rax, cs:__security_cookie
0x10040d2c1  xor     rax, rsp
0x10040d2c4  mov     [rbp+0E60h+var_10], rax
0x10040d2cb  xorps   xmm0, xmm0
0x10040d2ce  mov     [rsp+0F60h+StartupInfo.cb], 68h ; 'h'
0x10040d2d6  xor     eax, eax
0x10040d2d8  lea     rdx, [rbp+0E60h+Filename]; lpFilename
0x10040d2dc  mov     r8d, 104h; nSize
0x10040d2e2  mov     dword ptr [rbp+0E60h+StartupInfo.hStdError+4], eax
0x10040d2e5  xor     ecx, ecx; hModule
0x10040d2e7  mov     qword ptr [rsp+0F60h+ProcessInformation.dwProcessId], rax
0x10040d2ec  movups  xmmword ptr [rsp+0F60h+StartupInfo+4], xmm0
0x10040d2f1  movups  xmmword ptr [rbp+0E60h+StartupInfo.lpDesktop+4], xmm0
0x10040d2f5  movups  xmmword ptr [rbp+0E60h+StartupInfo.dwY], xmm0
0x10040d2f9  movups  xmmword ptr [rbp+0E60h+StartupInfo.dwYCountChars], xmm0
0x10040d2fd  movups  xmmword ptr [rbp+0E60h+StartupInfo+44h], xmm0
0x10040d301  movups  xmmword ptr [rbp+0E60h+StartupInfo.hStdInput+4], xmm0
0x10040d305  movups  xmmword ptr [rsp+0F60h+ProcessInformation.hProcess], xmm0
0x10040d30a  call    cs:__imp_GetModuleFileNameW
0x10040d310  xor     edi, edi
0x10040d312  lea     r9, [rbp+0E60h+Dir]; Dir
0x10040d319  mov     [rsp+0F60h+ExtCount], rdi; ExtCount
0x10040d31e  lea     rdx, [rbp+0E60h+Drive]; Drive
0x10040d322  mov     [rsp+0F60h+Ext], rdi; Ext
0x10040d327  lea     rcx, [rbp+0E60h+Filename]; FullPath
0x10040d32b  mov     [rsp+0F60h+FilenameCount], rdi; FilenameCount
0x10040d330  mov     qword ptr [rsp+0F60h+dwCreationFlags], rdi; Filename
0x10040d335  lea     r8d, [rdi+4]; DriveCount
0x10040d339  mov     [rsp+0F60h+DirCount], 101h; DirCount
0x10040d342  mov     [rbp+0E60h+var_C3A], di
0x10040d349  call    cs:__imp__wsplitpath_s
0x10040d34f  test    eax, eax
0x10040d351  jz      short loc_10040D3A6
0x10040d353  mov     ecx, 80070057h
0x10040d358  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040d35e  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040d364  lea     rbx, aFailedToWsplit; "Failed to _wsplitpath_s."
0x10040d36b  mov     [rsp+0F60h+dwCreationFlags], 80070057h
0x10040d373  mov     r9, rax; struct __crt_locale_pointers *
0x10040d376  mov     [rsp+0F60h+DirCount], rbx
0x10040d37b  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040d382  mov     edx, 200h; unsigned __int64
0x10040d387  lea     rcx, [rbp+0E60h+Buffer]; Buffer
0x10040d38e  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040d393  mov     rcx, rbx
0x10040d396  test    eax, eax
0x10040d398  js      short loc_10040D3A1
0x10040d39a  lea     rcx, [rbp+0E60h+Buffer]; char *
0x10040d3a1  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040d3a6  lea     rax, aSqlagentSqlage; "SqlAgent\\SqlAgent.exe"
0x10040d3ad  mov     edx, 104h; unsigned __int64
0x10040d3b2  mov     qword ptr [rsp+0F60h+dwCreationFlags], rax
0x10040d3b7  lea     r9, [rbp+0E60h+Drive]
0x10040d3bb  lea     rax, [rbp+0E60h+Dir]
0x10040d3c2  lea     r8, aSSS; "%s%s%s"
0x10040d3c9  mov     [rsp+0F60h+DirCount], rax
0x10040d3ce  lea     rcx, [rbp+0E60h+ApplicationName]; Buffer
0x10040d3d5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10040d3da  mov     ebx, eax
0x10040d3dc  test    eax, eax
0x10040d3de  jns     short loc_10040D42F
0x10040d3e0  lfence
0x10040d3e3  mov     ecx, eax
0x10040d3e5  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040d3eb  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040d3f1  mov     [rsp+0F60h+dwCreationFlags], ebx
0x10040d3f5  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040d3fc  lea     rbx, aFailedToLaunch_0; "Failed to launch sql agent."
0x10040d403  mov     r9, rax; struct __crt_locale_pointers *
0x10040d406  mov     edx, 200h; unsigned __int64
0x10040d40b  mov     [rsp+0F60h+DirCount], rbx
0x10040d410  lea     rcx, [rbp+0E60h+var_A30]; Buffer
0x10040d417  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040d41c  mov     rcx, rbx
0x10040d41f  test    eax, eax
0x10040d421  js      short loc_10040D42A
0x10040d423  lea     rcx, [rbp+0E60h+var_A30]; char *
0x10040d42a  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040d42f  movzx   eax, word ptr cs:aSqlagentExeCXd+28h; ""
0x10040d436  lea     rdx, [rbp+0E60h+CommandLine]; lpCommandLine
0x10040d43a  movups  xmm0, xmmword ptr cs:aSqlagentExeCXd; "sqlagent.exe -c -xdb"
0x10040d441  mov     [rbp+0E60h+var_E50], ax
0x10040d445  lea     rax, [rsp+0F60h+ProcessInformation]
0x10040d44a  movups  xmm1, xmmword ptr cs:aSqlagentExeCXd+10h; ".exe -c -xdb"
0x10040d451  mov     [rsp+0F60h+lpProcessInformation], rax; lpProcessInformation
0x10040d456  lea     rcx, [rbp+0E60h+ApplicationName]; lpApplicationName
0x10040d45d  lea     rax, [rsp+0F60h+StartupInfo]
0x10040d462  xor     r9d, r9d; lpThreadAttributes
0x10040d465  mov     [rsp+0F60h+ExtCount], rax; lpStartupInfo
0x10040d46a  xor     r8d, r8d; lpProcessAttributes
0x10040d46d  mov     [rsp+0F60h+Ext], rdi; lpCurrentDirectory
0x10040d472  movups  xmmword ptr [rbp+0E60h+CommandLine], xmm0
0x10040d476  mov     [rsp+0F60h+FilenameCount], rdi; lpEnvironment
0x10040d47b  movsd   xmm0, qword ptr cs:aSqlagentExeCXd+20h; "-xdb"
0x10040d483  mov     [rsp+0F60h+dwCreationFlags], 8010000h; dwCreationFlags
0x10040d48b  mov     dword ptr [rsp+0F60h+DirCount], edi; bInheritHandles
0x10040d48f  movups  [rbp+0E60h+var_E68], xmm1
0x10040d493  movsd   [rbp+0E60h+var_E58], xmm0
0x10040d498  call    cs:__imp_CreateProcessW
0x10040d49e  test    eax, eax
0x10040d4a0  jnz     short loc_10040D50A
0x10040d4a2  call    cs:__imp_GetLastError
0x10040d4a8  mov     ebx, eax
0x10040d4aa  test    eax, eax
0x10040d4ac  jle     short loc_10040D4B7
0x10040d4ae  movzx   ebx, ax
0x10040d4b1  or      ebx, 80070000h
0x10040d4b7  test    ebx, ebx
0x10040d4b9  jns     short loc_10040D50A
0x10040d4bb  lfence
0x10040d4be  mov     ecx, ebx
0x10040d4c0  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040d4c6  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040d4cc  mov     [rsp+0F60h+dwCreationFlags], ebx
0x10040d4d0  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040d4d7  lea     rbx, aFailedToLaunch; "Failed to launch sqlagent."
0x10040d4de  mov     r9, rax; struct __crt_locale_pointers *
0x10040d4e1  mov     edx, 200h; unsigned __int64
0x10040d4e6  mov     [rsp+0F60h+DirCount], rbx
0x10040d4eb  lea     rcx, [rbp+0E60h+var_830]; Buffer
0x10040d4f2  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040d4f7  mov     rcx, rbx
0x10040d4fa  test    eax, eax
0x10040d4fc  js      short loc_10040D505
0x10040d4fe  lea     rcx, [rbp+0E60h+var_830]; char *
0x10040d505  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040d50a  mov     rdx, [rsp+0F60h+ProcessInformation.hProcess]; hObject
0x10040d50f  lea     r8, ?SqlAgentProcessExitCallback@@YAXPEAXE@Z; Callback
0x10040d516  mov     [rsp+0F60h+dwCreationFlags], 8; dwFlags
0x10040d51e  lea     rcx, [rsp+0F60h+phNewWaitObject]; phNewWaitObject
0x10040d523  xor     r9d, r9d; Context
0x10040d526  mov     dword ptr [rsp+0F60h+DirCount], 0FFFFFFFFh; dwMilliseconds
0x10040d52e  call    cs:__imp_RegisterWaitForSingleObject
0x10040d534  test    eax, eax
0x10040d536  jnz     short loc_10040D5A0
0x10040d538  call    cs:__imp_GetLastError
0x10040d53e  mov     ebx, eax
0x10040d540  test    eax, eax
0x10040d542  jle     short loc_10040D54D
0x10040d544  movzx   ebx, ax
0x10040d547  or      ebx, 80070000h
0x10040d54d  test    ebx, ebx
0x10040d54f  jns     short loc_10040D5A0
0x10040d551  lfence
0x10040d554  mov     ecx, ebx
0x10040d556  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10040d55c  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10040d562  mov     [rsp+0F60h+dwCreationFlags], ebx
0x10040d566  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10040d56d  lea     rbx, aFailedToRegist; "Failed to register sql agent exit callb"...
0x10040d574  mov     r9, rax; struct __crt_locale_pointers *
0x10040d577  mov     edx, 200h; unsigned __int64
0x10040d57c  mov     [rsp+0F60h+DirCount], rbx
0x10040d581  lea     rcx, [rbp+0E60h+var_630]; Buffer
0x10040d588  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10040d58d  mov     rcx, rbx
0x10040d590  test    eax, eax
0x10040d592  js      short loc_10040D59B
0x10040d594  lea     rcx, [rbp+0E60h+var_630]; char *
0x10040d59b  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10040d5a0  mov     rcx, [rbp+0E60h+var_10]
0x10040d5a7  xor     rcx, rsp; StackCookie
0x10040d5aa  call    __security_check_cookie
0x10040d5af  lea     r11, [rsp+0F60h+var_s0]
0x10040d5b7  mov     rbx, [r11+10h]
0x10040d5bb  mov     rdi, [r11+18h]
0x10040d5bf  mov     rsp, r11
0x10040d5c2  pop     rbp
0x10040d5c3  retn
```
