# RunExe(ushort const *,ushort const *,int)

- ea: `0x18003cf58`
- end: `0x18003d153`
- name: `?RunExe@@YAJPEBG0H@Z`
- size: `507`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800411f0`
- `0x1800412f0`

## callees

- `0x180007824`
- `0x18003cf58`
- `0x18004d030`
- `0x18004d350`
- `0x180064c30`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003d0fb`
- `KERNEL32!CloseHandle` at `0x18003d110`
- `KERNEL32!CloseHandle` at `0x18003d11f`
- `KERNEL32!CloseHandle` at `0x18003d0fb`
- `KERNEL32!CloseHandle` at `0x18003d110`
- `KERNEL32!CloseHandle` at `0x18003d11f`
- `KERNEL32!CreateFileW` at `0x18003d04a`
- `KERNEL32!CreateFileW` at `0x18003d04a`
- `KERNEL32!WaitForSingleObject` at `0x18003d0c1`
- `KERNEL32!WaitForSingleObject` at `0x18003d0c1`
- `KERNEL32!GetExitCodeProcess` at `0x18003d0d5`
- `KERNEL32!GetExitCodeProcess` at `0x18003d0d5`
- `KERNEL32!CreateProcessW` at `0x18003d0a4`
- `KERNEL32!CreateProcessW` at `0x18003d0a4`

## pseudocode

```c
__int64 __fastcall RunExe(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rdi
  unsigned int LastWin32Error; // ebx
  HANDLE v8; // rax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+68h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ApplicationName[520]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR CommandLine[2048]; // [rsp+510h] [rbp+410h] BYREF

  v6 = -1;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  v11 = 0;
  CommandLine[0] = 0;
  ApplicationName[0] = 0;
  *(_OWORD *)&ProcessInformation.hThread = 0;
  LastWin32Error = StringCchCatW(ApplicationName, 0x208u, a1);
  if ( !LastWin32Error )
  {
    LastWin32Error = StringCchCatW(CommandLine, 0x800u, a2);
    if ( !LastWin32Error )
    {
      if ( a3 )
      {
        SecurityAttributes.nLength = 24;
        SecurityAttributes.lpSecurityDescriptor = 0;
        SecurityAttributes.bInheritHandle = 1;
        v8 = CreateFileW(L"nul", 0x80u, 1u, &SecurityAttributes, 3u, 0, 0);
        v6 = (__int64)v8;
        if ( v8 != (HANDLE)-1LL )
        {
          StartupInfo.dwFlags = 256;
          StartupInfo.hStdInput = v8;
          StartupInfo.hStdOutput = v8;
          StartupInfo.hStdError = v8;
        }
      }
      if ( CreateProcessW(
             ApplicationName,
             CommandLine,
             0,
             0,
             1,
             0,
             0,
             0,
             &StartupInfo,
             (LPPROCESS_INFORMATION)&ProcessInformation.hThread)
        && WaitForSingleObject(ProcessInformation.hThread, 0xFFFFFFFF) != -1
        && GetExitCodeProcess(ProcessInformation.hThread, (LPDWORD)&ProcessInformation) )
      {
        if ( LODWORD(ProcessInformation.hProcess) )
          LastWin32Error = -2147467259;
      }
      else
      {
        LastWin32Error = GetLastWin32Error();
      }
    }
  }
  if ( (unsigned __int64)(*(_QWORD *)&ProcessInformation.dwProcessId - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)&ProcessInformation.dwProcessId);
  if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(ProcessInformation.hThread);
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003cf58  mov     rax, rsp
0x18003cf5b  mov     [rax+8], rbx
0x18003cf5f  mov     [rax+10h], rsi
0x18003cf63  mov     [rax+18h], rdi
0x18003cf67  push    rbp
0x18003cf68  push    r14
0x18003cf6a  push    r15
0x18003cf6c  lea     rbp, [rax-1438h]
0x18003cf73  mov     eax, 1520h
0x18003cf78  call    _alloca_probe
0x18003cf7d  sub     rsp, rax
0x18003cf80  mov     rax, cs:__security_cookie
0x18003cf87  xor     rax, rsp
0x18003cf8a  mov     [rbp+1430h+var_20], rax
0x18003cf91  mov     esi, r8d
0x18003cf94  mov     r14, rdx
0x18003cf97  mov     rbx, rcx
0x18003cf9a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003cf9e  xor     edx, edx; Val
0x18003cfa0  lea     rcx, [rbp+1430h+StartupInfo+4]; void *
0x18003cfa4  lea     r8d, [rdi+65h]; Size
0x18003cfa8  call    memset_0
0x18003cfad  xorps   xmm0, xmm0
0x18003cfb0  mov     [rbp+1430h+StartupInfo.cb], 68h ; 'h'
0x18003cfb7  xor     eax, eax
0x18003cfb9  lea     rcx, [rbp+1430h+ApplicationName]; unsigned __int16 *
0x18003cfbd  xor     r15d, r15d
0x18003cfc0  mov     [rsp+1530h+var_14C8], rax
0x18003cfc5  mov     r8, rbx; unsigned __int16 *
0x18003cfc8  mov     [rbp+1430h+CommandLine], r15w
0x18003cfd0  mov     edx, 208h; unsigned __int64
0x18003cfd5  mov     [rbp+1430h+ApplicationName], r15w
0x18003cfda  movups  xmmword ptr [rsp+1530h+ProcessInformation.hThread], xmm0
0x18003cfdf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003cfe4  mov     ebx, eax
0x18003cfe6  test    eax, eax
0x18003cfe8  jnz     loc_18003D0EC
0x18003cfee  mov     r8, r14; unsigned __int16 *
0x18003cff1  lea     rcx, [rbp+1430h+CommandLine]; unsigned __int16 *
0x18003cff8  mov     edx, 800h; unsigned __int64
0x18003cffd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d002  mov     ebx, eax
0x18003d004  test    eax, eax
0x18003d006  jnz     loc_18003D0EC
0x18003d00c  lea     r14d, [rdi+2]
0x18003d010  test    esi, esi
0x18003d012  jz      short loc_18003D06C
0x18003d014  mov     [rsp+1530h+hTemplateFile], r15; hTemplateFile
0x18003d019  lea     r9, [rsp+1530h+SecurityAttributes]; lpSecurityAttributes
0x18003d01e  mov     [rsp+1530h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18003d023  lea     edx, [r14+7Fh]; dwDesiredAccess
0x18003d027  mov     r8d, r14d; dwShareMode
0x18003d02a  mov     [rsp+1530h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d032  lea     rcx, aNul; "nul"
0x18003d039  mov     [rsp+1530h+SecurityAttributes.nLength], 18h
0x18003d041  mov     [rsp+1530h+SecurityAttributes.lpSecurityDescriptor], r15
0x18003d046  mov     [rbp+1430h+SecurityAttributes.bInheritHandle], r14d
0x18003d04a  call    cs:__imp_CreateFileW
0x18003d050  mov     rdi, rax
0x18003d053  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d057  jz      short loc_18003D06C
0x18003d059  mov     [rbp+1430h+StartupInfo.dwFlags], 100h
0x18003d060  mov     [rbp+1430h+StartupInfo.hStdInput], rax
0x18003d064  mov     [rbp+1430h+StartupInfo.hStdOutput], rax
0x18003d068  mov     [rbp+1430h+StartupInfo.hStdError], rax
0x18003d06c  lea     rax, [rsp+1530h+ProcessInformation.hThread]
0x18003d071  xor     r9d, r9d; lpThreadAttributes
0x18003d074  mov     [rsp+1530h+lpProcessInformation], rax; lpProcessInformation
0x18003d079  lea     rdx, [rbp+1430h+CommandLine]; lpCommandLine
0x18003d080  lea     rax, [rbp+1430h+StartupInfo]
0x18003d084  xor     r8d, r8d; lpProcessAttributes
0x18003d087  mov     [rsp+1530h+lpStartupInfo], rax; lpStartupInfo
0x18003d08c  lea     rcx, [rbp+1430h+ApplicationName]; lpApplicationName
0x18003d090  mov     [rsp+1530h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18003d095  mov     [rsp+1530h+hTemplateFile], r15; lpEnvironment
0x18003d09a  mov     [rsp+1530h+dwFlagsAndAttributes], r15d; dwCreationFlags
0x18003d09f  mov     [rsp+1530h+dwCreationDisposition], r14d; bInheritHandles
0x18003d0a4  call    cs:__imp_CreateProcessW
0x18003d0aa  test    eax, eax
0x18003d0ac  jnz     short loc_18003D0B7
0x18003d0ae  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003d0b3  mov     ebx, eax
0x18003d0b5  jmp     short loc_18003D0EC
0x18003d0b7  mov     rcx, [rsp+1530h+ProcessInformation.hThread]; hHandle
0x18003d0bc  or      esi, 0FFFFFFFFh
0x18003d0bf  mov     edx, esi; dwMilliseconds
0x18003d0c1  call    cs:__imp_WaitForSingleObject
0x18003d0c7  cmp     eax, esi
0x18003d0c9  jz      short loc_18003D0AE
0x18003d0cb  mov     rcx, [rsp+1530h+ProcessInformation.hThread]; hProcess
0x18003d0d0  lea     rdx, [rsp+1530h+ProcessInformation]; lpExitCode
0x18003d0d5  call    cs:__imp_GetExitCodeProcess
0x18003d0db  test    eax, eax
0x18003d0dd  jz      short loc_18003D0AE
0x18003d0df  cmp     dword ptr [rsp+1530h+ProcessInformation.hProcess], r15d
0x18003d0e4  mov     eax, 80004005h
0x18003d0e9  cmovnz  ebx, eax
0x18003d0ec  mov     rcx, qword ptr [rsp+1530h+ProcessInformation.dwProcessId]; hObject
0x18003d0f1  lea     rax, [rcx-1]
0x18003d0f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d0f9  ja      short loc_18003D101
0x18003d0fb  call    cs:__imp_CloseHandle
0x18003d101  mov     rcx, [rsp+1530h+ProcessInformation.hThread]; hObject
0x18003d106  lea     rax, [rcx-1]
0x18003d10a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d10e  ja      short loc_18003D116
0x18003d110  call    cs:__imp_CloseHandle
0x18003d116  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003d11a  jz      short loc_18003D125
0x18003d11c  mov     rcx, rdi; hObject
0x18003d11f  call    cs:__imp_CloseHandle
0x18003d125  mov     eax, ebx
0x18003d127  mov     rcx, [rbp+1430h+var_20]
0x18003d12e  xor     rcx, rsp; StackCookie
0x18003d131  call    __security_check_cookie
0x18003d136  lea     r11, [rsp+1530h+var_10]
0x18003d13e  mov     rbx, [r11+20h]
0x18003d142  mov     rsi, [r11+28h]
0x18003d146  mov     rdi, [r11+30h]
0x18003d14a  mov     rsp, r11
0x18003d14d  pop     r15
0x18003d14f  pop     r14
0x18003d151  pop     rbp
0x18003d152  retn
```
