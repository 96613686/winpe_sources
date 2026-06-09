# CReflectedDumpServerLauncher::CreateWerfaultInProcessContext(void *,wchar_t const *,ulong,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001e81c`
- end: `0x18001ec84`
- name: `?CreateWerfaultInProcessContext@CReflectedDumpServerLauncher@@AEAAJPEAXPEB_WKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@2@Z`
- size: `1128`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f040`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x180007cf8`
- `0x18000caf0`
- `0x18000cb10`
- `0x18000ce58`
- `0x18001e81c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001eb2b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001eb2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e8de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e8de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ea22`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ea22`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e9aa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e9aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ea0e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001eb8c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ea0e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001eb8c`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18001e9e5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18001e9e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e90c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e91c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e90c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e91c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eb9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec56`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001e9cc`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001e9cc`
- `profapi!__imp_CreateEnvBlock` at `0x18001e97a`
- `profapi!__imp_CreateEnvBlock` at `0x18001e97a`
- `profapi!__imp_DestroyEnvBlock` at `0x18001e93b`
- `profapi!__imp_DestroyEnvBlock` at `0x18001e969`
- `profapi!__imp_DestroyEnvBlock` at `0x18001ebcb`
- `profapi!__imp_DestroyEnvBlock` at `0x18001ec42`
- `profapi!__imp_DestroyEnvBlock` at `0x18001e93b`
- `profapi!__imp_DestroyEnvBlock` at `0x18001e969`
- `profapi!__imp_DestroyEnvBlock` at `0x18001ebcb`
- `profapi!__imp_DestroyEnvBlock` at `0x18001ec42`

## pseudocode

```c
__int64 __fastcall CReflectedDumpServerLauncher::CreateWerfaultInProcessContext(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        void **a6)
{
  void **v8; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  int LastError; // ebx
  HANDLE v12; // rcx
  bool v13; // cc
  int v14; // eax
  unsigned __int64 v15; // rdx
  const char *v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  int lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION hObject; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpEnvironment; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL Wow64Process; // [rsp+88h] [rbp-78h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR CommandLine[264]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+458h]

  hToken = 0;
  lpEnvironment = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&hObject, 0, sizeof(hObject));
  memset_0(Buffer, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  if ( !a2 || !a3 || !a5 )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)0x80070057LL,
      lpThreadAttributes);
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    memset(&hObject, 0, sizeof(hObject));
    v12 = hToken;
    v13 = (unsigned __int64)hToken + 1 <= 1;
    goto LABEL_56;
  }
  v8 = (void **)tlx::replace<tlx::file_handle_traits>(&hToken);
  if ( !OpenProcessToken(a2, 0xBu, v8) )
  {
    v10 = 153;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                  v9);
LABEL_7:
    if ( hObject.hProcess )
      CloseHandle(hObject.hProcess);
    if ( hObject.hThread )
      CloseHandle(hObject.hThread);
    memset(&hObject, 0, sizeof(hObject));
    if ( lpEnvironment )
      DestroyEnvBlock();
    v12 = hToken;
    v13 = (unsigned __int64)hToken + 1 <= 1;
LABEL_56:
    if ( !v13 )
      CloseHandle(v12);
    return (unsigned int)LastError;
  }
  lpEnvironment = 0;
  v14 = CreateEnvBlock(&lpEnvironment, hToken, 0);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)(unsigned int)v14,
      lpThreadAttributes);
    goto LABEL_7;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v10 = 157;
    goto LABEL_6;
  }
  Wow64Process = 0;
  if ( IsWow64Process(a2, &Wow64Process) && Wow64Process )
  {
    if ( GetSystemWow64DirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      v17 = 172;
LABEL_22:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v17,
                    (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
                    v16);
LABEL_23:
      RevertToSelf();
      goto LABEL_7;
    }
  }
  else if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    v17 = 179;
    goto LABEL_22;
  }
  LastError = StringCchCatW(Buffer, v15, L"\\werfault.exe");
  if ( LastError < 0 )
  {
    v18 = 184;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\windows\\feedback\\core\\wersvc\\lib\\reflectionserver.cpp",
      (const char *)(unsigned int)LastError,
      lpThreadAttributes);
    goto LABEL_23;
  }
  lpThreadAttributes = a3;
  LastError = StringCchPrintfW(CommandLine, 0x104u, L"%s %s", Buffer);
  if ( LastError < 0 )
  {
    v18 = 191;
    goto LABEL_28;
  }
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = (LPWSTR)&dword_180039414;
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( !CreateProcessAsUserW(hToken, Buffer, CommandLine, 0, 0, 0, 0x404u, lpEnvironment, 0, &StartupInfo, &hObject) )
  {
    v17 = 212;
    goto LABEL_22;
  }
  v19 = *a5;
  *a5 = hObject.hProcess;
  hObject.hProcess = 0;
  if ( (unsigned __int64)v19 + 1 > 1 )
    CloseHandle(v19);
  if ( a6 )
  {
    v20 = *a6;
    *a6 = hObject.hThread;
    hObject.hThread = 0;
    if ( (unsigned __int64)v20 + 1 > 1 )
      CloseHandle(v20);
  }
  RevertToSelf();
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  memset(&hObject, 0, sizeof(hObject));
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( (unsigned __int64)hToken + 1 > 1 )
    CloseHandle(hToken);
  return 0;
}

```

## disassembly

```asm
0x18001e81c  mov     [rsp-8+arg_0], rbx
0x18001e821  push    rbp
0x18001e822  push    rsi
0x18001e823  push    rdi
0x18001e824  push    r14
0x18001e826  push    r15
0x18001e828  lea     rbp, [rsp-430h]
0x18001e830  sub     rsp, 530h
0x18001e837  mov     rax, cs:__security_cookie
0x18001e83e  xor     rax, rsp
0x18001e841  mov     [rbp+450h+var_30], rax
0x18001e848  mov     rdi, [rbp+450h+arg_28]
0x18001e84f  lea     rcx, [rbp+450h+StartupInfo]; void *
0x18001e853  mov     rsi, [rbp+450h+arg_20]
0x18001e85a  mov     r14, rdx
0x18001e85d  xor     edx, edx; Val
0x18001e85f  mov     [rbp+450h+hToken], 0
0x18001e867  mov     r15, r8
0x18001e86a  mov     [rsp+550h+var_4D8], 0
0x18001e873  lea     r8d, [rdx+68h]; Size
0x18001e877  call    memset_0
0x18001e87c  xorps   xmm0, xmm0
0x18001e87f  lea     rcx, [rbp+450h+Buffer]; void *
0x18001e883  xor     eax, eax
0x18001e885  mov     ebx, 208h
0x18001e88a  mov     r8d, ebx; Size
0x18001e88d  mov     [rsp+550h+var_4E0], rax
0x18001e892  xor     edx, edx; Val
0x18001e894  movups  xmmword ptr [rsp+550h+hObject], xmm0
0x18001e899  call    memset_0
0x18001e89e  mov     r8d, ebx; Size
0x18001e8a1  lea     rcx, [rbp+450h+CommandLine]; void *
0x18001e8a8  xor     edx, edx; Val
0x18001e8aa  call    memset_0
0x18001e8af  test    r14, r14
0x18001e8b2  jz      loc_18001EBE9
0x18001e8b8  test    r15, r15
0x18001e8bb  jz      loc_18001EBE9
0x18001e8c1  test    rsi, rsi
0x18001e8c4  jz      loc_18001EBE9
0x18001e8ca  lea     rcx, [rbp+450h+hToken]
0x18001e8ce  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001e8d3  mov     r8, rax; TokenHandle
0x18001e8d6  mov     edx, 0Bh; DesiredAccess
0x18001e8db  mov     rcx, r14; ProcessHandle
0x18001e8de  call    cs:__imp_OpenProcessToken
0x18001e8e4  test    eax, eax
0x18001e8e6  jnz     short loc_18001E952
0x18001e8e8  mov     edx, 99h; void *
0x18001e8ed  mov     rcx, [rbp+458h]; this
0x18001e8f4  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001e8fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e900  mov     ebx, eax
0x18001e902  mov     rcx, [rsp+550h+hObject]; hObject
0x18001e907  test    rcx, rcx
0x18001e90a  jz      short loc_18001E912
0x18001e90c  call    cs:__imp_CloseHandle
0x18001e912  mov     rcx, [rsp+550h+hObject+8]; hObject
0x18001e917  test    rcx, rcx
0x18001e91a  jz      short loc_18001E922
0x18001e91c  call    cs:__imp_CloseHandle
0x18001e922  mov     rcx, [rsp+550h+var_4D8]
0x18001e927  xor     eax, eax
0x18001e929  mov     [rsp+550h+var_4E0], rax
0x18001e92e  xorps   xmm0, xmm0
0x18001e931  movups  xmmword ptr [rsp+550h+hObject], xmm0
0x18001e936  test    rcx, rcx
0x18001e939  jz      short loc_18001E941
0x18001e93b  call    cs:__imp_DestroyEnvBlock
0x18001e941  mov     rcx, [rbp+450h+hToken]
0x18001e945  lea     rax, [rcx+1]
0x18001e949  cmp     rax, 1
0x18001e94d  jmp     loc_18001EC54
0x18001e952  mov     rcx, [rsp+550h+var_4D8]
0x18001e957  mov     rbx, [rbp+450h+hToken]
0x18001e95b  mov     [rsp+550h+var_4D8], 0
0x18001e964  test    rcx, rcx
0x18001e967  jz      short loc_18001E96F
0x18001e969  call    cs:__imp_DestroyEnvBlock
0x18001e96f  xor     r8d, r8d
0x18001e972  lea     rcx, [rsp+550h+var_4D8]
0x18001e977  mov     rdx, rbx
0x18001e97a  call    cs:__imp_CreateEnvBlock
0x18001e980  mov     ebx, eax
0x18001e982  test    eax, eax
0x18001e984  jns     short loc_18001E9A6
0x18001e986  mov     rcx, [rbp+458h]; this
0x18001e98d  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001e994  mov     r9d, eax; char *
0x18001e997  mov     edx, 9Bh; void *
0x18001e99c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9a1  jmp     loc_18001E902
0x18001e9a6  mov     rcx, [rbp+450h+hToken]; hToken
0x18001e9aa  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e9b0  test    eax, eax
0x18001e9b2  jnz     short loc_18001E9BE
0x18001e9b4  mov     edx, 9Dh
0x18001e9b9  jmp     loc_18001E8ED
0x18001e9be  lea     rdx, [rbp+450h+Wow64Process]; Wow64Process
0x18001e9c2  mov     [rbp+450h+Wow64Process], 0
0x18001e9c9  mov     rcx, r14; hProcess
0x18001e9cc  call    cs:__imp_IsWow64Process
0x18001e9d2  test    eax, eax
0x18001e9d4  jz      short loc_18001EA19
0x18001e9d6  cmp     [rbp+450h+Wow64Process], 0
0x18001e9da  jz      short loc_18001EA19
0x18001e9dc  mov     edx, 104h; uSize
0x18001e9e1  lea     rcx, [rbp+450h+Buffer]; lpBuffer
0x18001e9e5  call    cs:__imp_GetSystemWow64DirectoryW
0x18001e9eb  dec     eax
0x18001e9ed  cmp     eax, 103h
0x18001e9f2  jbe     short loc_18001EA38
0x18001e9f4  mov     edx, 0ACh; void *
0x18001e9f9  mov     rcx, [rbp+458h]; this
0x18001ea00  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001ea07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ea0c  mov     ebx, eax
0x18001ea0e  call    cs:__imp_RevertToSelf
0x18001ea14  jmp     loc_18001E902
0x18001ea19  mov     edx, 104h; uSize
0x18001ea1e  lea     rcx, [rbp+450h+Buffer]; lpBuffer
0x18001ea22  call    cs:__imp_GetSystemDirectoryW
0x18001ea28  dec     eax
0x18001ea2a  cmp     eax, 103h
0x18001ea2f  jbe     short loc_18001EA38
0x18001ea31  mov     edx, 0B3h
0x18001ea36  jmp     short loc_18001E9F9
0x18001ea38  lea     r8, aWerfaultExe; "\\werfault.exe"
0x18001ea3f  lea     rcx, [rbp+450h+Buffer]; wchar_t *
0x18001ea43  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001ea48  mov     ebx, eax
0x18001ea4a  test    eax, eax
0x18001ea4c  jns     short loc_18001EA6B
0x18001ea4e  mov     edx, 0B8h; void *
0x18001ea53  mov     rcx, [rbp+458h]; this
0x18001ea5a  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001ea61  mov     r9d, ebx; char *
0x18001ea64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea69  jmp     short loc_18001EA0E
0x18001ea6b  lea     r9, [rbp+450h+Buffer]
0x18001ea6f  mov     [rsp+550h+lpThreadAttributes], r15
0x18001ea74  lea     r8, aSS_0; "%s %s"
0x18001ea7b  mov     edx, 104h; unsigned __int64
0x18001ea80  lea     rcx, [rbp+450h+CommandLine]; wchar_t *
0x18001ea87  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001ea8c  mov     ebx, eax
0x18001ea8e  test    eax, eax
0x18001ea90  jns     short loc_18001EA99
0x18001ea92  mov     edx, 0BFh
0x18001ea97  jmp     short loc_18001EA53
0x18001ea99  mov     rcx, [rsp+550h+hObject]; hObject
0x18001ea9e  lea     rax, dword_180039414
0x18001eaa5  mov     [rbp+450h+StartupInfo.cb], 68h ; 'h'
0x18001eaac  mov     [rbp+450h+StartupInfo.lpDesktop], rax
0x18001eab0  test    rcx, rcx
0x18001eab3  jz      short loc_18001EABB
0x18001eab5  call    cs:__imp_CloseHandle
0x18001eabb  mov     rcx, [rsp+550h+hObject+8]; hObject
0x18001eac0  test    rcx, rcx
0x18001eac3  jz      short loc_18001EACB
0x18001eac5  call    cs:__imp_CloseHandle
0x18001eacb  xor     eax, eax
0x18001eacd  lea     rcx, [rsp+550h+hObject]
0x18001ead2  mov     [rsp+550h+lpProcessInformation], rcx; lpProcessInformation
0x18001ead7  lea     r8, [rbp+450h+CommandLine]; lpCommandLine
0x18001eade  lea     rcx, [rbp+450h+StartupInfo]
0x18001eae2  mov     [rsp+550h+var_4E0], rax
0x18001eae7  mov     rax, [rsp+550h+var_4D8]
0x18001eaec  lea     rdx, [rbp+450h+Buffer]; lpApplicationName
0x18001eaf0  mov     [rsp+550h+lpStartupInfo], rcx; lpStartupInfo
0x18001eaf5  xorps   xmm0, xmm0
0x18001eaf8  mov     rcx, [rbp+450h+hToken]; hToken
0x18001eafc  xor     r9d, r9d; lpProcessAttributes
0x18001eaff  mov     [rsp+550h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001eb08  mov     [rsp+550h+lpEnvironment], rax; lpEnvironment
0x18001eb0d  mov     [rsp+550h+dwCreationFlags], 404h; dwCreationFlags
0x18001eb15  mov     [rsp+550h+bInheritHandles], 0; bInheritHandles
0x18001eb1d  mov     [rsp+550h+lpThreadAttributes], 0; lpThreadAttributes
0x18001eb26  movups  xmmword ptr [rsp+550h+hObject], xmm0
0x18001eb2b  call    cs:__imp_CreateProcessAsUserW
0x18001eb31  test    eax, eax
0x18001eb33  jnz     short loc_18001EB3F
0x18001eb35  mov     edx, 0D4h
0x18001eb3a  jmp     loc_18001E9F9
0x18001eb3f  mov     rax, [rsp+550h+hObject]
0x18001eb44  mov     rcx, [rsi]; hObject
0x18001eb47  mov     [rsi], rax
0x18001eb4a  mov     [rsp+550h+hObject], 0
0x18001eb53  lea     rax, [rcx+1]
0x18001eb57  cmp     rax, 1
0x18001eb5b  jbe     short loc_18001EB63
0x18001eb5d  call    cs:__imp_CloseHandle
0x18001eb63  test    rdi, rdi
0x18001eb66  jz      short loc_18001EB8C
0x18001eb68  mov     rax, [rsp+550h+hObject+8]
0x18001eb6d  mov     rcx, [rdi]; hObject
0x18001eb70  mov     [rdi], rax
0x18001eb73  mov     [rsp+550h+hObject+8], 0
0x18001eb7c  lea     rax, [rcx+1]
0x18001eb80  cmp     rax, 1
0x18001eb84  jbe     short loc_18001EB8C
0x18001eb86  call    cs:__imp_CloseHandle
0x18001eb8c  call    cs:__imp_RevertToSelf
0x18001eb92  mov     rcx, [rsp+550h+hObject]; hObject
0x18001eb97  test    rcx, rcx
0x18001eb9a  jz      short loc_18001EBA2
0x18001eb9c  call    cs:__imp_CloseHandle
0x18001eba2  mov     rcx, [rsp+550h+hObject+8]; hObject
0x18001eba7  test    rcx, rcx
0x18001ebaa  jz      short loc_18001EBB2
0x18001ebac  call    cs:__imp_CloseHandle
0x18001ebb2  mov     rcx, [rsp+550h+var_4D8]
0x18001ebb7  xor     eax, eax
0x18001ebb9  mov     [rsp+550h+var_4E0], rax
0x18001ebbe  xorps   xmm0, xmm0
0x18001ebc1  movups  xmmword ptr [rsp+550h+hObject], xmm0
0x18001ebc6  test    rcx, rcx
0x18001ebc9  jz      short loc_18001EBD1
0x18001ebcb  call    cs:__imp_DestroyEnvBlock
0x18001ebd1  mov     rcx, [rbp+450h+hToken]; hObject
0x18001ebd5  lea     rax, [rcx+1]
0x18001ebd9  cmp     rax, 1
0x18001ebdd  jbe     short loc_18001EBE5
0x18001ebdf  call    cs:__imp_CloseHandle
0x18001ebe5  xor     eax, eax
0x18001ebe7  jmp     short loc_18001EC5E
0x18001ebe9  mov     rcx, [rbp+458h]; this
0x18001ebf0  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\wersv"...
0x18001ebf7  mov     ebx, 80070057h
0x18001ebfc  mov     edx, 93h; void *
0x18001ec01  mov     r9d, ebx; char *
0x18001ec04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec09  mov     rcx, [rsp+550h+hObject]; hObject
0x18001ec0e  test    rcx, rcx
0x18001ec11  jz      short loc_18001EC19
0x18001ec13  call    cs:__imp_CloseHandle
0x18001ec19  mov     rcx, [rsp+550h+hObject+8]; hObject
0x18001ec1e  test    rcx, rcx
0x18001ec21  jz      short loc_18001EC29
0x18001ec23  call    cs:__imp_CloseHandle
0x18001ec29  mov     rcx, [rsp+550h+var_4D8]
0x18001ec2e  xor     eax, eax
0x18001ec30  mov     [rsp+550h+var_4E0], rax
0x18001ec35  xorps   xmm0, xmm0
0x18001ec38  movups  xmmword ptr [rsp+550h+hObject], xmm0
0x18001ec3d  test    rcx, rcx
0x18001ec40  jz      short loc_18001EC48
0x18001ec42  call    cs:__imp_DestroyEnvBlock
0x18001ec48  mov     rcx, [rbp+450h+hToken]; hObject
0x18001ec4c  lea     rdx, [rcx+1]
0x18001ec50  cmp     rdx, 1
0x18001ec54  jbe     short loc_18001EC5C
0x18001ec56  call    cs:__imp_CloseHandle
0x18001ec5c  mov     eax, ebx
0x18001ec5e  mov     rcx, [rbp+450h+var_30]
0x18001ec65  xor     rcx, rsp; StackCookie
0x18001ec68  call    __security_check_cookie
0x18001ec6d  mov     rbx, [rsp+550h+arg_0]
0x18001ec75  add     rsp, 530h
0x18001ec7c  pop     r15
0x18001ec7e  pop     r14
0x18001ec80  pop     rdi
0x18001ec81  pop     rsi
0x18001ec82  pop     rbp
0x18001ec83  retn
```
