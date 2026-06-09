# _RunAsImpersonatedUser(ushort const *)

- ea: `0x18000e7d0`
- end: `0x18000eb5b`
- name: `?_RunAsImpersonatedUser@@YAJPEBG@Z`
- size: `907`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008ec0`
- `0x18000b020`
- `0x18000c2a0`

## callees

- `0x18000c8e8`
- `0x18000e7d0`
- `0x180010880`
- `0x1800108e4`
- `0x180012d6e`
- `0x180012db0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e87f`
- `KERNEL32!GetLastError` at `0x18000e9be`
- `KERNEL32!GetLastError` at `0x18000e87f`
- `KERNEL32!GetLastError` at `0x18000e9be`
- `KERNEL32!GetCurrentThreadId` at `0x18000e974`
- `KERNEL32!GetCurrentThreadId` at `0x18000e974`
- `KERNEL32!CloseHandle` at `0x18000eaa1`
- `KERNEL32!CloseHandle` at `0x18000eac0`
- `KERNEL32!CloseHandle` at `0x18000eb11`
- `KERNEL32!CloseHandle` at `0x18000eb30`
- `KERNEL32!CloseHandle` at `0x18000eaa1`
- `KERNEL32!CloseHandle` at `0x18000eac0`
- `KERNEL32!CloseHandle` at `0x18000eb11`
- `KERNEL32!CloseHandle` at `0x18000eb30`
- `KERNEL32!WaitForSingleObject` at `0x18000ea5c`
- `KERNEL32!WaitForSingleObject` at `0x18000ea5c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000e86f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000e86f`
- `KERNEL32!GetCurrentThread` at `0x18000e8b6`
- `KERNEL32!GetCurrentThread` at `0x18000e8b6`
- `KERNEL32!GetExitCodeProcess` at `0x18000ea72`
- `KERNEL32!GetExitCodeProcess` at `0x18000ea72`
- `ADVAPI32!CreateProcessWithTokenW` at `0x18000ea40`
- `ADVAPI32!CreateProcessWithTokenW` at `0x18000ea40`
- `ADVAPI32!DuplicateTokenEx` at `0x18000e909`
- `ADVAPI32!DuplicateTokenEx` at `0x18000e909`
- `ADVAPI32!OpenThreadToken` at `0x18000e8d7`
- `ADVAPI32!OpenThreadToken` at `0x18000e8d7`
- `USER32!CloseDesktop` at `0x18000eadd`
- `USER32!CloseDesktop` at `0x18000eaf1`
- `USER32!CloseDesktop` at `0x18000eadd`
- `USER32!CloseDesktop` at `0x18000eaf1`
- `USER32!SetThreadDesktop` at `0x18000e9dc`
- `USER32!SetThreadDesktop` at `0x18000e9dc`
- `USER32!CreateDesktopW` at `0x18000e9aa`
- `USER32!CreateDesktopW` at `0x18000e9aa`
- `USER32!GetThreadDesktop` at `0x18000e982`
- `USER32!GetThreadDesktop` at `0x18000e982`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e945`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e945`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e921`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e921`

## string_xrefs

- `0x18000e863`: `"%SystemRoot%\System32\rundll32.exe" "%SystemRoot%\System32\winethc.dll",`

## pseudocode

```c
__int64 __fastcall _RunAsImpersonatedUser(const unsigned __int16 *a1)
{
  HDESK DesktopW; // rsi
  HDESK ThreadDesktop; // r14
  unsigned __int64 v4; // rdx
  signed int LastError; // eax
  int v6; // ebx
  int v7; // ebx
  HANDLE CurrentThread; // rax
  DWORD CurrentThreadId; // eax
  signed int v10; // eax
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  void *hObject; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  GUID pguid; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[104]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Dst[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  ExitCode = 0;
  memset_0(Dst, 0, 0x208u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  TokenHandle = 0;
  hToken = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  hObject = 0;
  pguid = 0;
  memset_0(sz, 0, 0xC8u);
  DesktopW = 0;
  ThreadDesktop = 0;
  if ( !ExpandEnvironmentStringsW(
          L"\"%SystemRoot%\\System32\\rundll32.exe\" \"%SystemRoot%\\System32\\winethc.dll\",",
          Dst,
          0x104u) )
    goto LABEL_2;
  v6 = StringCchCatW(Dst, v4, a1);
  if ( v6 < 0 )
    goto LABEL_21;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle)
    || !DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
    goto LABEL_2;
  }
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
    goto LABEL_21;
  if ( !StringFromGUID2(&pguid, sz, 100) )
  {
LABEL_2:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError <= 0 )
      goto LABEL_21;
LABEL_3:
    v7 = (unsigned __int16)LastError;
LABEL_20:
    v6 = v7 | 0x80070000;
    goto LABEL_21;
  }
  LastError = SuspendImpersonate(&hObject);
  if ( LastError )
  {
    if ( LastError <= 0 )
    {
      v6 = LastError;
      goto LABEL_21;
    }
    goto LABEL_3;
  }
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  DesktopW = CreateDesktopW(sz, 0, 0, 0, 0x10000000u, 0);
  if ( !DesktopW )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
  }
  SetThreadDesktop(ThreadDesktop);
  if ( DesktopW )
  {
    StartupInfo.lpDesktop = sz;
    StartupInfo.cb = 104;
    if ( CreateProcessWithTokenW(hToken, 1u, 0, Dst, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      {
        v6 = ExitCode;
        if ( (int)ExitCode <= 0 )
          goto LABEL_21;
        v7 = (unsigned __int16)ExitCode;
        goto LABEL_20;
      }
    }
    goto LABEL_2;
  }
LABEL_21:
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( DesktopW )
    CloseDesktop(DesktopW);
  if ( ThreadDesktop )
    CloseDesktop(ThreadDesktop);
  ResumeImpersonate(&hObject);
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e7d0  push    rbp
0x18000e7d2  push    rbx
0x18000e7d3  push    rsi
0x18000e7d4  push    r14
0x18000e7d6  lea     rbp, [rsp-308h]
0x18000e7de  sub     rsp, 408h
0x18000e7e5  mov     rax, cs:__security_cookie
0x18000e7ec  xor     rax, rsp
0x18000e7ef  mov     [rbp+320h+var_30], rax
0x18000e7f6  mov     rbx, rcx
0x18000e7f9  mov     [rsp+420h+ExitCode], 0
0x18000e801  lea     rcx, [rbp+320h+Dst]; void *
0x18000e808  xor     edx, edx; Val
0x18000e80a  mov     r8d, 208h; Size
0x18000e810  call    memset_0
0x18000e815  xor     edx, edx; Val
0x18000e817  lea     rcx, [rbp+320h+StartupInfo]; void *
0x18000e81b  lea     r8d, [rdx+68h]; Size
0x18000e81f  call    memset_0
0x18000e824  xor     eax, eax
0x18000e826  lea     rcx, [rbp+320h+sz]; void *
0x18000e82a  xorps   xmm0, xmm0
0x18000e82d  mov     qword ptr [rbp+320h+ProcessInformation.dwProcessId], rax
0x18000e831  xor     edx, edx; Val
0x18000e833  mov     [rsp+420h+TokenHandle], rax
0x18000e838  mov     r8d, 0C8h; Size
0x18000e83e  mov     [rsp+420h+hToken], rax
0x18000e843  movups  xmmword ptr [rsp+420h+ProcessInformation.hProcess], xmm0
0x18000e848  mov     [rsp+420h+hObject], rax
0x18000e84d  movups  xmmword ptr [rbp+320h+pguid.Data1], xmm0
0x18000e851  call    memset_0
0x18000e856  mov     r8d, 104h; nSize
0x18000e85c  lea     rdx, [rbp+320h+Dst]; lpDst
0x18000e863  lea     rcx, aSystemrootSyst; "\"%SystemRoot%\\System32\\rundll32.exe"...
0x18000e86a  xor     esi, esi
0x18000e86c  xor     r14d, r14d
0x18000e86f  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e876  nop     dword ptr [rax+rax+00h]
0x18000e87b  test    eax, eax
0x18000e87d  jnz     short loc_18000E89D
0x18000e87f  call    cs:__imp_GetLastError
0x18000e886  nop     dword ptr [rax+rax+00h]
0x18000e88b  mov     ebx, eax
0x18000e88d  test    eax, eax
0x18000e88f  jle     loc_18000EA97
0x18000e895  movzx   ebx, ax
0x18000e898  jmp     loc_18000EA91
0x18000e89d  mov     r8, rbx; unsigned __int16 *
0x18000e8a0  lea     rcx, [rbp+320h+Dst]; unsigned __int16 *
0x18000e8a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e8ac  mov     ebx, eax
0x18000e8ae  test    eax, eax
0x18000e8b0  js      loc_18000EA97
0x18000e8b6  call    cs:__imp_GetCurrentThread
0x18000e8bd  nop     dword ptr [rax+rax+00h]
0x18000e8c2  mov     ebx, 2000000h
0x18000e8c7  lea     r9, [rsp+420h+TokenHandle]; TokenHandle
0x18000e8cc  mov     rcx, rax; ThreadHandle
0x18000e8cf  mov     edx, ebx; DesiredAccess
0x18000e8d1  mov     r8d, 1; OpenAsSelf
0x18000e8d7  call    cs:__imp_OpenThreadToken
0x18000e8de  nop     dword ptr [rax+rax+00h]
0x18000e8e3  test    eax, eax
0x18000e8e5  jz      short loc_18000E87F
0x18000e8e7  mov     rcx, [rsp+420h+TokenHandle]; hExistingToken
0x18000e8ec  lea     rax, [rsp+420h+hToken]
0x18000e8f1  mov     [rsp+420h+phNewToken], rax; phNewToken
0x18000e8f6  mov     r9d, 2; ImpersonationLevel
0x18000e8fc  xor     r8d, r8d; lpTokenAttributes
0x18000e8ff  mov     [rsp+420h+TokenType], 1; TokenType
0x18000e907  mov     edx, ebx; dwDesiredAccess
0x18000e909  call    cs:__imp_DuplicateTokenEx
0x18000e910  nop     dword ptr [rax+rax+00h]
0x18000e915  test    eax, eax
0x18000e917  jz      loc_18000E87F
0x18000e91d  lea     rcx, [rbp+320h+pguid]; pguid
0x18000e921  call    cs:__imp_CoCreateGuid
0x18000e928  nop     dword ptr [rax+rax+00h]
0x18000e92d  mov     ebx, eax
0x18000e92f  test    eax, eax
0x18000e931  js      loc_18000EA97
0x18000e937  mov     r8d, 64h ; 'd'; cchMax
0x18000e93d  lea     rdx, [rbp+320h+sz]; lpsz
0x18000e941  lea     rcx, [rbp+320h+pguid]; rguid
0x18000e945  call    cs:__imp_StringFromGUID2
0x18000e94c  nop     dword ptr [rax+rax+00h]
0x18000e951  test    eax, eax
0x18000e953  jz      loc_18000E87F
0x18000e959  lea     rcx, [rsp+420h+hObject]; hObject
0x18000e95e  call    ?SuspendImpersonate@@YAKPEAPEAX@Z; SuspendImpersonate(void * *)
0x18000e963  test    eax, eax
0x18000e965  jz      short loc_18000E974
0x18000e967  jg      loc_18000E895
0x18000e96d  mov     ebx, eax
0x18000e96f  jmp     loc_18000EA97
0x18000e974  call    cs:__imp_GetCurrentThreadId
0x18000e97b  nop     dword ptr [rax+rax+00h]
0x18000e980  mov     ecx, eax; dwThreadId
0x18000e982  call    cs:__imp_GetThreadDesktop
0x18000e989  nop     dword ptr [rax+rax+00h]
0x18000e98e  xor     r9d, r9d; dwFlags
0x18000e991  mov     [rsp+420h+phNewToken], rsi; lpsa
0x18000e996  xor     r8d, r8d; pDevmode
0x18000e999  mov     [rsp+420h+TokenType], 10000000h; dwDesiredAccess
0x18000e9a1  xor     edx, edx; lpszDevice
0x18000e9a3  lea     rcx, [rbp+320h+sz]; lpszDesktop
0x18000e9a7  mov     r14, rax
0x18000e9aa  call    cs:__imp_CreateDesktopW
0x18000e9b1  nop     dword ptr [rax+rax+00h]
0x18000e9b6  mov     rsi, rax
0x18000e9b9  test    rax, rax
0x18000e9bc  jnz     short loc_18000E9D9
0x18000e9be  call    cs:__imp_GetLastError
0x18000e9c5  nop     dword ptr [rax+rax+00h]
0x18000e9ca  mov     ebx, eax
0x18000e9cc  test    eax, eax
0x18000e9ce  jle     short loc_18000E9D9
0x18000e9d0  movzx   ebx, ax
0x18000e9d3  or      ebx, 80070000h
0x18000e9d9  mov     rcx, r14; hDesktop
0x18000e9dc  call    cs:__imp_SetThreadDesktop
0x18000e9e3  nop     dword ptr [rax+rax+00h]
0x18000e9e8  test    rsi, rsi
0x18000e9eb  jz      loc_18000EA97
0x18000e9f1  mov     rcx, [rsp+420h+hToken]; hToken
0x18000e9f6  lea     rax, [rbp+320h+sz]
0x18000e9fa  mov     [rbp+320h+StartupInfo.lpDesktop], rax
0x18000e9fe  lea     r9, [rbp+320h+Dst]; lpCommandLine
0x18000ea05  lea     rax, [rsp+420h+ProcessInformation]
0x18000ea0a  mov     [rbp+320h+StartupInfo.cb], 68h ; 'h'
0x18000ea11  mov     [rsp+420h+lpProcessInformation], rax; lpProcessInformation
0x18000ea16  xor     r8d, r8d; lpApplicationName
0x18000ea19  lea     rax, [rbp+320h+StartupInfo]
0x18000ea1d  mov     [rsp+420h+lpStartupInfo], rax; lpStartupInfo
0x18000ea22  mov     [rsp+420h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000ea2b  mov     [rsp+420h+phNewToken], 0; lpEnvironment
0x18000ea34  lea     edx, [r8+1]; dwLogonFlags
0x18000ea38  mov     [rsp+420h+TokenType], 0; dwCreationFlags
0x18000ea40  call    cs:__imp_CreateProcessWithTokenW
0x18000ea47  nop     dword ptr [rax+rax+00h]
0x18000ea4c  test    eax, eax
0x18000ea4e  jz      loc_18000E87F
0x18000ea54  mov     rcx, [rsp+420h+ProcessInformation.hProcess]; hHandle
0x18000ea59  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ea5c  call    cs:__imp_WaitForSingleObject
0x18000ea63  nop     dword ptr [rax+rax+00h]
0x18000ea68  mov     rcx, [rsp+420h+ProcessInformation.hProcess]; hProcess
0x18000ea6d  lea     rdx, [rsp+420h+ExitCode]; lpExitCode
0x18000ea72  call    cs:__imp_GetExitCodeProcess
0x18000ea79  nop     dword ptr [rax+rax+00h]
0x18000ea7e  test    eax, eax
0x18000ea80  jz      loc_18000E87F
0x18000ea86  mov     ebx, [rsp+420h+ExitCode]
0x18000ea8a  test    ebx, ebx
0x18000ea8c  jle     short loc_18000EA97
0x18000ea8e  movzx   ebx, bx
0x18000ea91  or      ebx, 80070000h
0x18000ea97  mov     rcx, [rsp+420h+ProcessInformation.hThread]; hObject
0x18000ea9c  test    rcx, rcx
0x18000ea9f  jz      short loc_18000EAB6
0x18000eaa1  call    cs:__imp_CloseHandle
0x18000eaa8  nop     dword ptr [rax+rax+00h]
0x18000eaad  mov     [rsp+420h+ProcessInformation.hThread], 0
0x18000eab6  mov     rcx, [rsp+420h+ProcessInformation.hProcess]; hObject
0x18000eabb  test    rcx, rcx
0x18000eabe  jz      short loc_18000EAD5
0x18000eac0  call    cs:__imp_CloseHandle
0x18000eac7  nop     dword ptr [rax+rax+00h]
0x18000eacc  mov     [rsp+420h+ProcessInformation.hProcess], 0
0x18000ead5  test    rsi, rsi
0x18000ead8  jz      short loc_18000EAE9
0x18000eada  mov     rcx, rsi; hDesktop
0x18000eadd  call    cs:__imp_CloseDesktop
0x18000eae4  nop     dword ptr [rax+rax+00h]
0x18000eae9  test    r14, r14
0x18000eaec  jz      short loc_18000EAFD
0x18000eaee  mov     rcx, r14; hDesktop
0x18000eaf1  call    cs:__imp_CloseDesktop
0x18000eaf8  nop     dword ptr [rax+rax+00h]
0x18000eafd  lea     rcx, [rsp+420h+hObject]; void **
0x18000eb02  call    ?ResumeImpersonate@@YAKPEAPEAX@Z; ResumeImpersonate(void * *)
0x18000eb07  mov     rcx, [rsp+420h+hToken]; hObject
0x18000eb0c  test    rcx, rcx
0x18000eb0f  jz      short loc_18000EB26
0x18000eb11  call    cs:__imp_CloseHandle
0x18000eb18  nop     dword ptr [rax+rax+00h]
0x18000eb1d  mov     [rsp+420h+hToken], 0
0x18000eb26  mov     rcx, [rsp+420h+TokenHandle]; hObject
0x18000eb2b  test    rcx, rcx
0x18000eb2e  jz      short loc_18000EB3C
0x18000eb30  call    cs:__imp_CloseHandle
0x18000eb37  nop     dword ptr [rax+rax+00h]
0x18000eb3c  mov     eax, ebx
0x18000eb3e  mov     rcx, [rbp+320h+var_30]
0x18000eb45  xor     rcx, rsp; StackCookie
0x18000eb48  call    __security_check_cookie
0x18000eb4d  add     rsp, 408h
0x18000eb54  pop     r14
0x18000eb56  pop     rsi
0x18000eb57  pop     rbx
0x18000eb58  pop     rbp
0x18000eb59  retn
```
