# LaunchProcess(wchar_t *,wchar_t const *,void * *)

- ea: `0x1801bd250`
- end: `0x1801bd4ee`
- name: `?LaunchProcess@@YAJPEA_WPEB_WPEAPEAX@Z`
- size: `670`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, const wchar_t *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801bd4f4`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18012b618`
- `0x1801bd250`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801bd40b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801bd40b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801bd356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801bd356`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801bd368`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801bd368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd48f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd4a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd48f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bd4a1`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1801bd3bb`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1801bd3bb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801bd2eb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801bd30a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801bd2eb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1801bd30a`

## string_xrefs

- `0x1801bd2de`: `SeShutdownPrivilege`
- `0x1801bd303`: `SeRemoteShutdownPrivilege`
- `0x1801bd325`: `Attempting to create remote update deployment session CF host process with service process token`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall LaunchProcess(LPWSTR lpCommandLine, const wchar_t *a2, void **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HANDLE hThread; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  HANDLE CurrentProcess; // rax
  unsigned int LastError; // edi
  __int64 v12; // rdx
  int DeletePrivilegeCount; // [rsp+20h] [rbp-E0h]
  int DeletePrivilegeCounta; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  _LUID Luid[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v21; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( !lpCommandLine || !*lpCommandLine )
  {
    v5 = -2147024809;
    v6 = 100;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 101;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
      (const char *)v5,
      DeletePrivilegeCount);
    return v5;
  }
  hThread = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  hObject = 0;
  hToken = 0;
  v21 = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", Luid) )
  {
    v9 = 114;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
                  v8);
    goto LABEL_22;
  }
  if ( !LookupPrivilegeValueW(0, L"SeRemoteShutdownPrivilege", (PLUID)&Luid[1].HighPart) )
  {
    v9 = 115;
    goto LABEL_15;
  }
  StartupInfo.cb = 104;
  WUTrace(
    0,
    0,
    0x1000000,
    5,
    0,
    L"Attempting to create remote update deployment session CF host process with service process token");
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xBu, &hObject) )
  {
    v9 = 125;
    goto LABEL_15;
  }
  if ( !CreateRestrictedToken(hObject, 0, 0, 0, 2u, (PLUID_AND_ATTRIBUTES)Luid, 0, 0, &hToken) )
  {
    v9 = 136;
    goto LABEL_15;
  }
  if ( !CreateProcessAsUserW(hToken, 0, lpCommandLine, 0, 0, 1, 0x400u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    v9 = 149;
    goto LABEL_15;
  }
  if ( ProcessInformation.hThread )
  {
    if ( ProcessInformation.hProcess )
    {
      hThread = ProcessInformation.hThread;
      *a3 = ProcessInformation.hProcess;
      LastError = 0;
      goto LABEL_22;
    }
    v12 = 152;
  }
  else
  {
    v12 = 151;
  }
  LastError = -2145120257;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DeploymentHelper\\DeploymentHelper.cpp",
    (const char *)0x80240FFFLL,
    DeletePrivilegeCounta);
LABEL_22:
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( hThread )
    CloseHandle(hThread);
  return LastError;
}

```

## disassembly

```asm
0x1801bd250  mov     [rsp-8+arg_8], rbx
0x1801bd255  mov     [rsp-8+arg_18], rsi
0x1801bd25a  push    rbp
0x1801bd25b  push    rdi
0x1801bd25c  push    r14
0x1801bd25e  lea     rbp, [rsp-20h]
0x1801bd263  sub     rsp, 120h
0x1801bd26a  mov     rax, cs:__security_cookie
0x1801bd271  xor     rax, rsp
0x1801bd274  mov     [rbp+30h+var_18], rax
0x1801bd278  xor     r14d, r14d
0x1801bd27b  mov     rsi, r8
0x1801bd27e  mov     rdi, rcx
0x1801bd281  test    rcx, rcx
0x1801bd284  jz      loc_1801BD4AB
0x1801bd28a  cmp     [rcx], r14w
0x1801bd28e  jz      loc_1801BD4AB
0x1801bd294  test    r8, r8
0x1801bd297  jnz     short loc_1801BD2A7
0x1801bd299  mov     ebx, 80004003h
0x1801bd29e  lea     edx, [r8+65h]
0x1801bd2a2  jmp     loc_1801BD4B5
0x1801bd2a7  xor     eax, eax
0x1801bd2a9  lea     rcx, [rbp+30h+StartupInfo]; void *
0x1801bd2ad  xorps   xmm0, xmm0
0x1801bd2b0  mov     qword ptr [rsp+130h+ProcessInformation.dwProcessId], rax
0x1801bd2b5  xor     edx, edx; Val
0x1801bd2b7  mov     rbx, r14
0x1801bd2ba  movups  xmmword ptr [rsp+130h+ProcessInformation.hProcess], xmm0
0x1801bd2bf  lea     r8d, [rax+68h]; Size
0x1801bd2c3  call    memset
0x1801bd2c8  xorps   xmm0, xmm0
0x1801bd2cb  mov     [rbp+30h+hObject], r14
0x1801bd2cf  xor     eax, eax
0x1801bd2d1  mov     [rsp+130h+hToken], r14
0x1801bd2d6  lea     r8, [rbp+30h+Luid]; lpLuid
0x1801bd2da  mov     [rbp+30h+var_20], rax
0x1801bd2de  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x1801bd2e5  xor     ecx, ecx; lpSystemName
0x1801bd2e7  movups  xmmword ptr [rbp+30h+Luid.LowPart], xmm0
0x1801bd2eb  call    cs:__imp_LookupPrivilegeValueW
0x1801bd2f1  test    eax, eax
0x1801bd2f3  jnz     short loc_1801BD2FD
0x1801bd2f5  lea     edx, [rax+72h]
0x1801bd2f8  jmp     loc_1801BD41A
0x1801bd2fd  lea     r8, [rbp+30h+Luid.HighPart+8]; lpLuid
0x1801bd301  xor     ecx, ecx; lpSystemName
0x1801bd303  lea     rdx, aSeremoteshutdo; "SeRemoteShutdownPrivilege"
0x1801bd30a  call    cs:__imp_LookupPrivilegeValueW
0x1801bd310  test    eax, eax
0x1801bd312  jnz     short loc_1801BD31C
0x1801bd314  lea     edx, [rax+73h]
0x1801bd317  jmp     loc_1801BD41A
0x1801bd31c  xor     edx, edx
0x1801bd31e  mov     [rbp+30h+StartupInfo.cb], 68h ; 'h'
0x1801bd325  lea     rax, aAttemptingToCr; "Attempting to create remote update depl"...
0x1801bd32c  xor     ecx, ecx
0x1801bd32e  mov     [rsp+130h+PrivilegesToDelete], rax
0x1801bd333  mov     r8d, 1000000h
0x1801bd339  mov     qword ptr [rsp+130h+DeletePrivilegeCount], r14
0x1801bd33e  lea     r9d, [rdx+5]
0x1801bd342  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801bd347  mov     rcx, [rbp+30h+hObject]; hObject
0x1801bd34b  test    rcx, rcx
0x1801bd34e  jz      short loc_1801BD356
0x1801bd350  call    cs:__imp_CloseHandle
0x1801bd356  call    cs:__imp_GetCurrentProcess
0x1801bd35c  lea     r8, [rbp+30h+hObject]; TokenHandle
0x1801bd360  mov     edx, 0Bh; DesiredAccess
0x1801bd365  mov     rcx, rax; ProcessHandle
0x1801bd368  call    cs:__imp_OpenProcessToken
0x1801bd36e  test    eax, eax
0x1801bd370  jnz     short loc_1801BD37A
0x1801bd372  lea     edx, [rax+7Dh]
0x1801bd375  jmp     loc_1801BD41A
0x1801bd37a  mov     rcx, [rsp+130h+hToken]; hObject
0x1801bd37f  test    rcx, rcx
0x1801bd382  jz      short loc_1801BD38A
0x1801bd384  call    cs:__imp_CloseHandle
0x1801bd38a  mov     rcx, [rbp+30h+hObject]; ExistingTokenHandle
0x1801bd38e  lea     rax, [rsp+130h+hToken]
0x1801bd393  mov     [rsp+130h+NewTokenHandle], rax; NewTokenHandle
0x1801bd398  xor     r9d, r9d; SidsToDisable
0x1801bd39b  mov     [rsp+130h+SidsToRestrict], r14; SidsToRestrict
0x1801bd3a0  lea     rax, [rbp+30h+Luid]
0x1801bd3a4  mov     [rsp+130h+RestrictedSidCount], r14d; RestrictedSidCount
0x1801bd3a9  xor     r8d, r8d; DisableSidCount
0x1801bd3ac  mov     [rsp+130h+PrivilegesToDelete], rax; PrivilegesToDelete
0x1801bd3b1  xor     edx, edx; Flags
0x1801bd3b3  mov     [rsp+130h+DeletePrivilegeCount], 2; DeletePrivilegeCount
0x1801bd3bb  call    cs:__imp_CreateRestrictedToken
0x1801bd3c1  test    eax, eax
0x1801bd3c3  jnz     short loc_1801BD3CC
0x1801bd3c5  mov     edx, 88h
0x1801bd3ca  jmp     short loc_1801BD41A
0x1801bd3cc  mov     rcx, [rsp+130h+hToken]; hToken
0x1801bd3d1  lea     rax, [rsp+130h+ProcessInformation]
0x1801bd3d6  mov     [rsp+130h+lpProcessInformation], rax; lpProcessInformation
0x1801bd3db  xor     r9d, r9d; lpProcessAttributes
0x1801bd3de  lea     rax, [rbp+30h+StartupInfo]
0x1801bd3e2  mov     r8, rdi; lpCommandLine
0x1801bd3e5  mov     [rsp+130h+lpStartupInfo], rax; lpStartupInfo
0x1801bd3ea  xor     edx, edx; lpApplicationName
0x1801bd3ec  mov     [rsp+130h+NewTokenHandle], r14; lpCurrentDirectory
0x1801bd3f1  mov     [rsp+130h+SidsToRestrict], r14; lpEnvironment
0x1801bd3f6  mov     [rsp+130h+RestrictedSidCount], 400h; dwCreationFlags
0x1801bd3fe  mov     dword ptr [rsp+130h+PrivilegesToDelete], 1; bInheritHandles
0x1801bd406  mov     qword ptr [rsp+130h+DeletePrivilegeCount], r14; int
0x1801bd40b  call    cs:__imp_CreateProcessAsUserW
0x1801bd411  test    eax, eax
0x1801bd413  jnz     short loc_1801BD42E
0x1801bd415  mov     edx, 95h; void *
0x1801bd41a  mov     rcx, [rbp+38h]; this
0x1801bd41e  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd425  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801bd42a  mov     edi, eax
0x1801bd42c  jmp     short loc_1801BD471
0x1801bd42e  mov     rax, [rsp+130h+ProcessInformation.hThread]
0x1801bd433  test    rax, rax
0x1801bd436  jnz     short loc_1801BD43F
0x1801bd438  mov     edx, 97h
0x1801bd43d  jmp     short loc_1801BD44E
0x1801bd43f  mov     rcx, [rsp+130h+ProcessInformation.hProcess]
0x1801bd444  test    rcx, rcx
0x1801bd447  jnz     short loc_1801BD468
0x1801bd449  mov     edx, 98h; void *
0x1801bd44e  mov     rcx, [rbp+38h]; this
0x1801bd452  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd459  mov     edi, 80240FFFh
0x1801bd45e  mov     r9d, edi; char *
0x1801bd461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd466  jmp     short loc_1801BD471
0x1801bd468  mov     rbx, rax
0x1801bd46b  mov     [rsi], rcx
0x1801bd46e  mov     edi, r14d
0x1801bd471  mov     rcx, [rsp+130h+hToken]; hObject
0x1801bd476  test    rcx, rcx
0x1801bd479  jz      short loc_1801BD486
0x1801bd47b  call    cs:__imp_CloseHandle
0x1801bd481  mov     [rsp+130h+hToken], r14
0x1801bd486  mov     rcx, [rbp+30h+hObject]; hObject
0x1801bd48a  test    rcx, rcx
0x1801bd48d  jz      short loc_1801BD499
0x1801bd48f  call    cs:__imp_CloseHandle
0x1801bd495  mov     [rbp+30h+hObject], r14
0x1801bd499  test    rbx, rbx
0x1801bd49c  jz      short loc_1801BD4A7
0x1801bd49e  mov     rcx, rbx; hObject
0x1801bd4a1  call    cs:__imp_CloseHandle
0x1801bd4a7  mov     eax, edi
0x1801bd4a9  jmp     short loc_1801BD4CA
0x1801bd4ab  mov     ebx, 80070057h
0x1801bd4b0  mov     edx, 64h ; 'd'; void *
0x1801bd4b5  mov     rcx, [rbp+38h]; this
0x1801bd4b9  lea     r8, aCW1SSrcClientL_26; "C:\\__w\\1\\s\\src\\Client\\lib\\Deploy"...
0x1801bd4c0  mov     r9d, ebx; char *
0x1801bd4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bd4c8  mov     eax, ebx
0x1801bd4ca  mov     rcx, [rbp+30h+var_18]
0x1801bd4ce  xor     rcx, rsp; StackCookie
0x1801bd4d1  call    __security_check_cookie
0x1801bd4d6  lea     r11, [rsp+130h+var_10]
0x1801bd4de  mov     rbx, [r11+28h]
0x1801bd4e2  mov     rsi, [r11+38h]
0x1801bd4e6  mov     rsp, r11
0x1801bd4e9  pop     r14
0x1801bd4eb  pop     rdi
0x1801bd4ec  pop     rbp
0x1801bd4ed  retn
```
