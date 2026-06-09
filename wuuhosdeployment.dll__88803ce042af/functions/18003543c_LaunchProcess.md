# LaunchProcess

- ea: `0x18003543c`
- end: `0x1800356ff`
- name: `LaunchProcess`
- size: `707`
- prototype: `__int64 __fastcall(LPWSTR lpCommandLine, char, HANDLE *, DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035de4`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000956c`
- `0x18000c0b4`
- `0x18000fcfc`
- `0x180010358`
- `0x180010f54`
- `0x180034d04`
- `0x180035088`
- `0x18003543c`
- `0x180042630`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800355fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800355fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800356d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800356d9`
- `USERENV!DestroyEnvironmentBlock` at `0x1800356c5`
- `USERENV!DestroyEnvironmentBlock` at `0x1800356c5`
- `USERENV!CreateEnvironmentBlock` at `0x180035568`
- `USERENV!CreateEnvironmentBlock` at `0x180035568`

## string_xrefs

- `0x18003567a`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1800354a2`: `Attempting to launch remote process with user process token.`

## pseudocode

```c
__int64 __fastcall LaunchProcess(LPWSTR lpCommandLine, char a2, HANDLE *a3, DWORD *a4)
{
  __int64 v8; // rdx
  int v10; // eax
  unsigned int LastError; // edi
  char *v12; // rbx
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // rdx
  WCHAR *lpDesktop; // rax
  __int64 v17; // rdx
  bool v18; // cl
  DWORD dwProcessId; // edi
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // eax
  int lpThreadAttributes; // [rsp+20h] [rbp-B9h]
  int lpThreadAttributesa; // [rsp+20h] [rbp-B9h]
  HANDLE hToken; // [rsp+60h] [rbp-79h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-71h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-59h] BYREF
  LPVOID Environment; // [rsp+F0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( !a3 )
  {
    v8 = 201;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)0x80004003LL,
      lpThreadAttributes);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    v8 = 202;
    goto LABEL_3;
  }
  WUTrace(0, 0, 4096, 5);
  WUTrace(0, 0, 4096, 5);
  hToken = 0;
  v10 = CreateToken(&hToken);
  LastError = v10;
  v12 = (char *)hToken;
  if ( v10 >= 0 )
  {
    v13 = DumpUserTokenPrivileges(hToken);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
        (const char *)(unsigned int)v13,
        0);
    Environment = 0;
    if ( CreateEnvironmentBlock(&Environment, v12, 0) )
    {
      memset(&StartupInfo.cb + 1, 0, 0x64u);
      StartupInfo.cb = 104;
      lpDesktop = L"winsta0\\default";
      if ( !a2 )
        lpDesktop = StartupInfo.lpDesktop;
      StartupInfo.lpDesktop = lpDesktop;
      memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      if ( CreateProcessAsUserW(
             v12,
             0,
             lpCommandLine,
             0,
             0,
             0,
             0x400u,
             Environment,
             0,
             &StartupInfo,
             &ProcessInformation) )
      {
        if ( ProcessInformation.hThread )
        {
          if ( ProcessInformation.hProcess )
          {
            if ( CloseHandle(ProcessInformation.hThread) )
            {
              dwProcessId = ProcessInformation.dwProcessId;
              if ( (unsigned int)AreTestKeysAllowed(v18) )
              {
                if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                                     v20,
                                     L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                                     L"RemoteUHProcessRegisterPID",
                                     0) )
                {
                  v24 = RegSetDwordValue(v22, v21, v23, dwProcessId);
                  if ( v24 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0xC3,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                      (const char *)(unsigned int)v24,
                      lpThreadAttributesa);
                }
              }
              *a3 = ProcessInformation.hProcess;
              *a4 = ProcessInformation.dwProcessId;
              LastError = 0;
              goto LABEL_29;
            }
            v15 = 242;
            goto LABEL_23;
          }
          v17 = 240;
        }
        else
        {
          v17 = 239;
        }
        LastError = -2145112065;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
          (const char *)0x80242FFFLL,
          lpThreadAttributesa);
        goto LABEL_29;
      }
      v15 = 237;
    }
    else
    {
      v15 = 214;
    }
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
                  v14);
LABEL_29:
    if ( Environment )
      DestroyEnvironmentBlock(Environment);
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
    (const char *)(unsigned int)v10,
    0);
LABEL_31:
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  return LastError;
}

```

## disassembly

```asm
0x18003543c  push    rbp
0x18003543e  push    rbx
0x18003543f  push    rsi
0x180035440  push    rdi
0x180035441  push    r12
0x180035443  push    r14
0x180035445  push    r15
0x180035447  lea     rbp, [rsp-27h]
0x18003544c  sub     rsp, 100h
0x180035453  mov     rax, cs:__security_cookie
0x18003545a  xor     rax, rsp
0x18003545d  mov     [rbp+57h+var_38], rax
0x180035461  mov     rsi, r9
0x180035464  mov     r14, r8
0x180035467  mov     r12b, dl
0x18003546a  mov     r15, rcx
0x18003546d  test    r8, r8
0x180035470  jnz     short loc_180035496
0x180035472  mov     edx, 0C9h; void *
0x180035477  mov     ebx, 80004003h
0x18003547c  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035483  mov     r9d, ebx; char *
0x180035486  mov     rcx, [rbp+5Fh]; this
0x18003548a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003548f  mov     eax, ebx
0x180035491  jmp     loc_1800356E1
0x180035496  test    rsi, rsi
0x180035499  jnz     short loc_1800354A2
0x18003549b  mov     edx, 0CAh
0x1800354a0  jmp     short loc_180035477
0x1800354a2  lea     rax, aAttemptingToLa; "Attempting to launch remote process wit"...
0x1800354a9  mov     qword ptr [rsp+130h+bInheritHandles], rax
0x1800354ae  mov     [rsp+130h+lpThreadAttributes], 0
0x1800354b7  mov     edi, 5
0x1800354bc  mov     r9d, edi
0x1800354bf  mov     ebx, 1000h
0x1800354c4  mov     r8d, ebx
0x1800354c7  xor     edx, edx
0x1800354c9  xor     ecx, ecx
0x1800354cb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800354d0  mov     qword ptr [rsp+130h+dwCreationFlags], r15
0x1800354d5  lea     rax, aCmdLineWs; "Cmd Line: %ws"
0x1800354dc  mov     qword ptr [rsp+130h+bInheritHandles], rax
0x1800354e1  mov     [rsp+130h+lpThreadAttributes], 0; int
0x1800354ea  mov     r9d, edi
0x1800354ed  mov     r8d, ebx
0x1800354f0  xor     edx, edx
0x1800354f2  xor     ecx, ecx
0x1800354f4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800354f9  mov     [rbp+57h+hToken], 0
0x180035501  lea     rcx, [rbp+57h+hToken]
0x180035505  call    CreateToken
0x18003550a  mov     edi, eax
0x18003550c  mov     rbx, [rbp+57h+hToken]
0x180035510  test    eax, eax
0x180035512  jns     short loc_180035531
0x180035514  mov     rcx, [rbp+5Fh]; this
0x180035518  mov     r9d, eax; char *
0x18003551b  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035522  mov     edx, 0D0h; void *
0x180035527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003552c  jmp     loc_1800356CC
0x180035531  mov     rcx, rbx
0x180035534  call    DumpUserTokenPrivileges
0x180035539  mov     rcx, [rbp+5Fh]; this
0x18003553d  test    eax, eax
0x18003553f  jns     short loc_180035556
0x180035541  mov     r9d, eax; char *
0x180035544  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003554b  mov     edx, 0D1h; void *
0x180035550  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035555  nop
0x180035556  mov     [rbp+57h+Environment], 0
0x18003555e  xor     r8d, r8d; bInherit
0x180035561  mov     rdx, rbx; hToken
0x180035564  lea     rcx, [rbp+57h+Environment]; lpEnvironment
0x180035568  call    cs:__imp_CreateEnvironmentBlock
0x18003556e  test    eax, eax
0x180035570  jnz     short loc_18003557C
0x180035572  mov     edx, 0D6h
0x180035577  jmp     loc_180035650
0x18003557c  xor     edx, edx; Val
0x18003557e  lea     r8d, [rdx+64h]; Size
0x180035582  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x180035586  call    memset
0x18003558b  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180035592  lea     rax, aWinsta0Default; "winsta0\\default"
0x180035599  test    r12b, r12b
0x18003559c  cmovz   rax, [rbp+57h+StartupInfo.lpDesktop]
0x1800355a1  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x1800355a5  xorps   xmm0, xmm0
0x1800355a8  xor     eax, eax
0x1800355aa  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1800355ae  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1800355b2  mov     rax, [rbp+57h+Environment]
0x1800355b6  lea     rcx, [rbp+57h+ProcessInformation]
0x1800355ba  mov     [rsp+130h+lpProcessInformation], rcx; lpProcessInformation
0x1800355bf  lea     rcx, [rbp+57h+StartupInfo]
0x1800355c3  mov     [rsp+130h+lpStartupInfo], rcx; lpStartupInfo
0x1800355c8  mov     [rsp+130h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800355d1  mov     [rsp+130h+lpEnvironment], rax; lpEnvironment
0x1800355d6  mov     [rsp+130h+dwCreationFlags], 400h; dwCreationFlags
0x1800355de  mov     [rsp+130h+bInheritHandles], 0; bInheritHandles
0x1800355e6  mov     [rsp+130h+lpThreadAttributes], 0; int
0x1800355ef  xor     r9d, r9d; lpProcessAttributes
0x1800355f2  mov     r8, r15; lpCommandLine
0x1800355f5  xor     edx, edx; lpApplicationName
0x1800355f7  mov     rcx, rbx; hToken
0x1800355fa  call    cs:__imp_CreateProcessAsUserW
0x180035600  test    eax, eax
0x180035602  jnz     short loc_18003560B
0x180035604  mov     edx, 0EDh
0x180035609  jmp     short loc_180035650
0x18003560b  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18003560f  test    rcx, rcx
0x180035612  jnz     short loc_18003561B
0x180035614  mov     edx, 0EFh
0x180035619  jmp     short loc_180035627
0x18003561b  cmp     [rbp+57h+ProcessInformation.hProcess], 0
0x180035620  jnz     short loc_180035641
0x180035622  mov     edx, 0F0h; void *
0x180035627  mov     edi, 80242FFFh
0x18003562c  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035633  mov     r9d, edi; char *
0x180035636  mov     rcx, [rbp+5Fh]; this
0x18003563a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003563f  jmp     short loc_1800356BC
0x180035641  call    cs:__imp_CloseHandle
0x180035647  test    eax, eax
0x180035649  jnz     short loc_180035664
0x18003564b  mov     edx, 0F2h; void *
0x180035650  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035657  mov     rcx, [rbp+5Fh]; this
0x18003565b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035660  mov     edi, eax
0x180035662  jmp     short loc_1800356BC
0x180035664  mov     edi, [rbp+57h+ProcessInformation.dwProcessId]
0x180035667  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18003566c  test    eax, eax
0x18003566e  jz      short loc_1800356AE
0x180035670  xor     r9d, r9d
0x180035673  lea     r8, ?c_szRegRemoteUHProcessRegisterPID@@3QB_WB; "RemoteUHProcessRegisterPID"
0x18003567a  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035681  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x180035686  test    eax, eax
0x180035688  jz      short loc_1800356AE
0x18003568a  mov     r9d, edi
0x18003568d  call    ?RegSetDwordValue@@YAJPEAUHKEY__@@PEB_W1KW4RegistryHiveType@@@Z; RegSetDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong,RegistryHiveType)
0x180035692  mov     rcx, [rbp+5Fh]; this
0x180035696  test    eax, eax
0x180035698  jns     short loc_1800356AE
0x18003569a  mov     r9d, eax; char *
0x18003569d  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800356a4  mov     edx, 0C3h; void *
0x1800356a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800356ae  mov     rax, [rbp+57h+ProcessInformation.hProcess]
0x1800356b2  mov     [r14], rax
0x1800356b5  mov     eax, [rbp+57h+ProcessInformation.dwProcessId]
0x1800356b8  mov     [rsi], eax
0x1800356ba  xor     edi, edi
0x1800356bc  mov     rcx, [rbp+57h+Environment]; lpEnvironment
0x1800356c0  test    rcx, rcx
0x1800356c3  jz      short loc_1800356CC
0x1800356c5  call    cs:__imp_DestroyEnvironmentBlock
0x1800356cb  nop
0x1800356cc  lea     rdx, [rbx-1]
0x1800356d0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800356d4  ja      short loc_1800356DF
0x1800356d6  mov     rcx, rbx; hObject
0x1800356d9  call    cs:__imp_CloseHandle
0x1800356df  mov     eax, edi
0x1800356e1  mov     rcx, [rbp+57h+var_38]
0x1800356e5  xor     rcx, rsp; StackCookie
0x1800356e8  call    __security_check_cookie
0x1800356ed  add     rsp, 100h
0x1800356f4  pop     r15
0x1800356f6  pop     r14
0x1800356f8  pop     r12
0x1800356fa  pop     rdi
0x1800356fb  pop     rsi
0x1800356fc  pop     rbx
0x1800356fd  pop     rbp
0x1800356fe  retn
```
