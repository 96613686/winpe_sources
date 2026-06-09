# Microsoft::Diagnostics::Utils::Os::DumpProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64)

- ea: `0x18008b6b8`
- end: `0x18008bd07`
- name: `?DumpProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z`
- size: `1615`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800acf60`
- `0x1800e7680`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180032718`
- `0x180034d94`
- `0x180035698`
- `0x1800495cc`
- `0x180088da8`
- `0x18008b3c8`
- `0x18008b644`
- `0x18008b6b8`
- `0x18008bd1c`
- `0x18012de40`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008bbd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008bbd8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008b9b5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18008b9b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008b9a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008b9a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008b9ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008b9ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008b738`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008b738`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18008b833`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18008b833`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18008b7b8`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18008b7b8`

## string_xrefs

- `0x18008bb5d`: `dbghelp.dll`
- `0x18008bbd1`: `MiniDumpWriteDump`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::DumpProcess(
        unsigned int a1,
        _QWORD *a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int a5)
{
  __int64 v8; // rax
  HANDLE v9; // rbx
  const char *v10; // r9
  unsigned int LastError; // ebx
  const char *v13; // r9
  unsigned int v14; // ebx
  LPWSTR *v15; // rcx
  unsigned int SystemWow64Directory2W; // eax
  const char *v17; // r9
  unsigned int v18; // ebx
  __int64 v19; // rdx
  LPWSTR *v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  HANDLE CurrentProcess; // rax
  WCHAR *v24; // rcx
  UINT SystemDirectoryW; // eax
  const char *v26; // r9
  unsigned int v27; // ebx
  __int64 v28; // rdx
  LPWSTR *v29; // rax
  int v30; // eax
  const char *v31; // r9
  unsigned int v32; // ebx
  FARPROC ProcAddress; // rax
  const char *v34; // r9
  unsigned int v35; // ebx
  const char *v36; // r9
  unsigned int v37; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-D8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-D8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-D8h]
  __int64 v41; // [rsp+40h] [rbp-B8h] BYREF
  _WORD v42[2]; // [rsp+48h] [rbp-B0h] BYREF
  int v43; // [rsp+4Ch] [rbp-ACh] BYREF
  HMODULE hModule; // [rsp+50h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD v46[2]; // [rsp+70h] [rbp-88h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+80h] [rbp-78h] BYREF
  UINT uSize[2]; // [rsp+90h] [rbp-68h]
  unsigned __int64 v49; // [rsp+98h] [rbp-60h]
  _QWORD v50[4]; // [rsp+A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  v8 = std::wstring::wstring((__int64)v50, a4);
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v8 = *(_QWORD *)v8;
  v9 = CreateFileW((LPCWSTR)v8, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
  v41 = (__int64)v9;
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v50);
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4B2,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
    return LastError;
  }
  std::wstring::wstring(lpBuffer, 260, 0);
  v42[0] = 0;
  if ( !(unsigned int)IsWow64Process2(*a2, v42, 0) )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4BE,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
            v13);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
    return v14;
  }
  if ( v42[0] )
  {
    v15 = lpBuffer;
    if ( v49 > 7 )
      v15 = (LPWSTR *)lpBuffer[0];
    SystemWow64Directory2W = GetSystemWow64Directory2W(v15, uSize[0]);
    if ( !SystemWow64Directory2W )
    {
      v18 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4C8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v17);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
      return v18;
    }
    v19 = SystemWow64Directory2W;
    if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)0x8007007ALL,
        dwCreationDisposition);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
      return 2147942522LL;
    }
    v20 = lpBuffer;
    if ( v49 > 7 )
      v20 = (LPWSTR *)lpBuffer[0];
    if ( !*(_WORD *)v20 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CA,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)0x800700A1LL,
        dwCreationDisposition);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
      return 2147942561LL;
    }
    std::wstring::resize(lpBuffer, v19);
    v21 = Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc((LPCWSTR)lpBuffer, (__int64)&v41, a5);
    v22 = v21;
    if ( v21 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)(unsigned int)v21,
        dwCreationDispositiona);
    goto LABEL_20;
  }
  CurrentProcess = GetCurrentProcess();
  if ( a1 == GetProcessId(CurrentProcess) )
  {
    v24 = (WCHAR *)lpBuffer;
    if ( v49 > 7 )
      v24 = lpBuffer[0];
    SystemDirectoryW = GetSystemDirectoryW(v24, uSize[0]);
    if ( SystemDirectoryW )
    {
      v28 = SystemDirectoryW;
      if ( (unsigned __int64)SystemDirectoryW < *(_QWORD *)uSize )
      {
        v29 = lpBuffer;
        if ( v49 > 7 )
          v29 = (LPWSTR *)lpBuffer[0];
        if ( *(_WORD *)v29 )
        {
          std::wstring::resize(lpBuffer, v28);
          v30 = Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc((LPCWSTR)lpBuffer, (__int64)&v41, a5);
          v22 = v30;
          if ( v30 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4E7,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              (const char *)(unsigned int)v30,
              dwCreationDispositionb);
LABEL_20:
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
          return v22;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DF,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)0x800700A1LL,
          dwCreationDisposition);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
        return 2147942561LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
          (const char *)0x8007007ALL,
          dwCreationDisposition);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
        return 2147942522LL;
      }
    }
    else
    {
      v27 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4DD,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v26);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
      return v27;
    }
  }
  else
  {
    v46[0] = L"dbghelp.dll";
    v46[1] = 11;
    Microsoft::Diagnostics::Utils::Os::LoadSystemLibrary(&hModule, v46);
    if ( hModule )
    {
      ProcAddress = GetProcAddress(hModule, "MiniDumpWriteDump");
      if ( ProcAddress )
      {
        v43 = 0;
        v50[0] = Microsoft::Diagnostics::Utils::Os::MinidumpCallback;
        v50[1] = &v43;
        if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, HANDLE, _QWORD, _QWORD, _QWORD, _QWORD *))ProcAddress)(
               *a2,
               a1,
               v9,
               a3,
               0,
               0,
               v50) )
        {
          Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
          return 0;
        }
        else
        {
          v37 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x508,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v36);
          Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
          return v37;
        }
      }
      else
      {
        v35 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x4F3,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                v34);
        Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
        return v35;
      }
    }
    else
    {
      v32 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x4EC,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v31);
      Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&hModule);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
      return v32;
    }
  }
}

```

## disassembly

```asm
0x18008b6b8  mov     r11, rsp
0x18008b6bb  push    rbx
0x18008b6bc  push    rsi
0x18008b6bd  push    rdi
0x18008b6be  push    r14
0x18008b6c0  push    r15
0x18008b6c2  sub     rsp, 0D0h
0x18008b6c9  mov     rax, cs:__security_cookie
0x18008b6d0  xor     rax, rsp
0x18008b6d3  mov     [rsp+0F8h+var_38], rax
0x18008b6db  mov     r14d, r8d
0x18008b6de  mov     rsi, rdx
0x18008b6e1  mov     edi, ecx
0x18008b6e3  mov     qword ptr [rsp+0F8h+SecurityAttributes.nLength], 18h
0x18008b6ec  xor     r15d, r15d
0x18008b6ef  mov     [rsp+0F8h+SecurityAttributes.lpSecurityDescriptor], r15
0x18008b6f4  mov     qword ptr [rsp+0F8h+SecurityAttributes.bInheritHandle], 1
0x18008b6fd  mov     rdx, r9
0x18008b700  lea     rcx, [r11-58h]
0x18008b704  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18008b709  cmp     qword ptr [rax+18h], 7
0x18008b70e  jbe     short loc_18008B713
0x18008b710  mov     rax, [rax]
0x18008b713  mov     [rsp+0F8h+hTemplateFile], r15; hTemplateFile
0x18008b718  mov     [rsp+0F8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008b720  mov     [rsp+0F8h+dwCreationDisposition], 2; int
0x18008b728  lea     r9, [rsp+0F8h+SecurityAttributes]; lpSecurityAttributes
0x18008b72d  xor     r8d, r8d; dwShareMode
0x18008b730  mov     edx, 40000000h; dwDesiredAccess
0x18008b735  mov     rcx, rax; lpFileName
0x18008b738  call    cs:__imp_CreateFileW
0x18008b73f  nop     dword ptr [rax+rax+00h]
0x18008b744  mov     rbx, rax
0x18008b747  mov     [rsp+0F8h+var_B8], rax
0x18008b74c  lea     rcx, [rsp+0F8h+var_58]; this
0x18008b754  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b759  lea     rax, [rbx+1]
0x18008b75d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008b763  jnz     short loc_18008B791
0x18008b765  mov     rcx, [rsp+0F8h]; this
0x18008b76d  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b774  mov     edx, 4B2h; void *
0x18008b779  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b77e  mov     ebx, eax
0x18008b780  lea     rcx, [rsp+0F8h+var_B8]
0x18008b785  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b78a  mov     eax, ebx
0x18008b78c  jmp     loc_18008BCE7
0x18008b791  xor     r8d, r8d
0x18008b794  mov     edx, 104h
0x18008b799  lea     rcx, [rsp+0F8h+lpBuffer]
0x18008b7a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18008b7a6  nop
0x18008b7a7  mov     [rsp+0F8h+var_B0], r15w
0x18008b7ad  xor     r8d, r8d
0x18008b7b0  lea     rdx, [rsp+0F8h+var_B0]
0x18008b7b5  mov     rcx, [rsi]
0x18008b7b8  call    cs:__imp_IsWow64Process2
0x18008b7bf  nop     dword ptr [rax+rax+00h]
0x18008b7c4  test    eax, eax
0x18008b7c6  jnz     short loc_18008B802
0x18008b7c8  mov     rcx, [rsp+0F8h]; this
0x18008b7d0  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b7d7  mov     edx, 4BEh; void *
0x18008b7dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b7e1  mov     ebx, eax
0x18008b7e3  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008b7eb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b7f0  nop
0x18008b7f1  lea     rcx, [rsp+0F8h+var_B8]
0x18008b7f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b7fb  mov     eax, ebx
0x18008b7fd  jmp     loc_18008BCE7
0x18008b802  movzx   r8d, [rsp+0F8h+var_B0]
0x18008b808  test    r8w, r8w
0x18008b80c  jz      loc_18008B9A6
0x18008b812  lea     rcx, [rsp+0F8h+lpBuffer]
0x18008b81a  cmp     [rsp+0F8h+var_60], 7
0x18008b823  cmova   rcx, [rsp+0F8h+lpBuffer]
0x18008b82c  mov     edx, [rsp+0F8h+uSize]
0x18008b833  call    cs:__imp_GetSystemWow64Directory2W
0x18008b83a  nop     dword ptr [rax+rax+00h]
0x18008b83f  test    eax, eax
0x18008b841  jnz     short loc_18008B87D
0x18008b843  mov     rcx, [rsp+0F8h]; this
0x18008b84b  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b852  mov     edx, 4C8h; void *
0x18008b857  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008b85c  mov     ebx, eax
0x18008b85e  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008b866  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b86b  nop
0x18008b86c  lea     rcx, [rsp+0F8h+var_B8]
0x18008b871  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b876  mov     eax, ebx
0x18008b878  jmp     loc_18008BCE7
0x18008b87d  mov     edx, eax
0x18008b87f  cmp     rdx, qword ptr [rsp+0F8h+uSize]
0x18008b887  jb      short loc_18008B8CA
0x18008b889  mov     rcx, [rsp+0F8h]; this
0x18008b891  mov     ebx, 8007007Ah
0x18008b896  mov     r9d, ebx; char *
0x18008b899  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b8a0  mov     edx, 4C9h; void *
0x18008b8a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b8aa  nop
0x18008b8ab  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008b8b3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b8b8  nop
0x18008b8b9  lea     rcx, [rsp+0F8h+var_B8]
0x18008b8be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b8c3  mov     eax, ebx
0x18008b8c5  jmp     loc_18008BCE7
0x18008b8ca  lea     rax, [rsp+0F8h+lpBuffer]
0x18008b8d2  cmp     [rsp+0F8h+var_60], 7
0x18008b8db  cmova   rax, [rsp+0F8h+lpBuffer]
0x18008b8e4  cmp     [rax], r15w
0x18008b8e8  jnz     short loc_18008B92B
0x18008b8ea  mov     rcx, [rsp+0F8h]; this
0x18008b8f2  mov     ebx, 800700A1h
0x18008b8f7  mov     r9d, ebx; char *
0x18008b8fa  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b901  mov     edx, 4CAh; void *
0x18008b906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b90b  nop
0x18008b90c  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008b914  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b919  nop
0x18008b91a  lea     rcx, [rsp+0F8h+var_B8]
0x18008b91f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b924  mov     eax, ebx
0x18008b926  jmp     loc_18008BCE7
0x18008b92b  lea     rcx, [rsp+0F8h+lpBuffer]
0x18008b933  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18008b938  mov     rax, qword ptr [rsp+0F8h+arg_20]
0x18008b940  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; unsigned int
0x18008b945  lea     rax, [rsp+0F8h+var_B8]
0x18008b94a  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rax; int
0x18008b94f  mov     r9d, r14d
0x18008b952  mov     r8, rsi
0x18008b955  mov     edx, edi
0x18008b957  lea     rcx, [rsp+0F8h+lpBuffer]; lpSrc
0x18008b95f  call    ?LaunchDtDumpOutOfProc@Os@Utils@Diagnostics@Microsoft@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@8@_K@Z; Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc(std::wstring &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,unsigned __int64)
0x18008b964  mov     ebx, eax
0x18008b966  test    eax, eax
0x18008b968  jns     short loc_18008B987
0x18008b96a  mov     rcx, [rsp+0F8h]; this
0x18008b972  mov     r9d, eax; char *
0x18008b975  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008b97c  mov     edx, 4D2h; void *
0x18008b981  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b986  nop
0x18008b987  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008b98f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008b994  nop
0x18008b995  lea     rcx, [rsp+0F8h+var_B8]
0x18008b99a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008b99f  mov     eax, ebx
0x18008b9a1  jmp     loc_18008BCE7
0x18008b9a6  call    cs:__imp_GetCurrentProcess
0x18008b9ad  nop     dword ptr [rax+rax+00h]
0x18008b9b2  mov     rcx, rax; Process
0x18008b9b5  call    cs:__imp_GetProcessId
0x18008b9bc  nop     dword ptr [rax+rax+00h]
0x18008b9c1  cmp     edi, eax
0x18008b9c3  jnz     loc_18008BB5D
0x18008b9c9  lea     rcx, [rsp+0F8h+lpBuffer]
0x18008b9d1  cmp     [rsp+0F8h+var_60], 7
0x18008b9da  cmova   rcx, [rsp+0F8h+lpBuffer]; lpBuffer
0x18008b9e3  mov     edx, [rsp+0F8h+uSize]; uSize
0x18008b9ea  call    cs:__imp_GetSystemDirectoryW
0x18008b9f1  nop     dword ptr [rax+rax+00h]
0x18008b9f6  test    eax, eax
0x18008b9f8  jnz     short loc_18008BA34
0x18008b9fa  mov     rcx, [rsp+0F8h]; this
0x18008ba02  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008ba09  mov     edx, 4DDh; void *
0x18008ba0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008ba13  mov     ebx, eax
0x18008ba15  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008ba1d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008ba22  nop
0x18008ba23  lea     rcx, [rsp+0F8h+var_B8]
0x18008ba28  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008ba2d  mov     eax, ebx
0x18008ba2f  jmp     loc_18008BCE7
0x18008ba34  mov     edx, eax
0x18008ba36  cmp     rdx, qword ptr [rsp+0F8h+uSize]
0x18008ba3e  jb      short loc_18008BA81
0x18008ba40  mov     rcx, [rsp+0F8h]; this
0x18008ba48  mov     ebx, 8007007Ah
0x18008ba4d  mov     r9d, ebx; char *
0x18008ba50  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008ba57  mov     edx, 4DEh; void *
0x18008ba5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ba61  nop
0x18008ba62  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008ba6a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008ba6f  nop
0x18008ba70  lea     rcx, [rsp+0F8h+var_B8]
0x18008ba75  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008ba7a  mov     eax, ebx
0x18008ba7c  jmp     loc_18008BCE7
0x18008ba81  lea     rax, [rsp+0F8h+lpBuffer]
0x18008ba89  cmp     [rsp+0F8h+var_60], 7
0x18008ba92  cmova   rax, [rsp+0F8h+lpBuffer]
0x18008ba9b  cmp     [rax], r15w
0x18008ba9f  jnz     short loc_18008BAE2
0x18008baa1  mov     rcx, [rsp+0F8h]; this
0x18008baa9  mov     ebx, 800700A1h
0x18008baae  mov     r9d, ebx; char *
0x18008bab1  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008bab8  mov     edx, 4DFh; void *
0x18008babd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bac2  nop
0x18008bac3  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008bacb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008bad0  nop
0x18008bad1  lea     rcx, [rsp+0F8h+var_B8]
0x18008bad6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008badb  mov     eax, ebx
0x18008badd  jmp     loc_18008BCE7
0x18008bae2  lea     rcx, [rsp+0F8h+lpBuffer]
0x18008baea  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18008baef  mov     rax, qword ptr [rsp+0F8h+arg_20]
0x18008baf7  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rax; unsigned int
0x18008bafc  lea     rax, [rsp+0F8h+var_B8]
0x18008bb01  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rax; int
0x18008bb06  mov     r9d, r14d
0x18008bb09  mov     r8, rsi
0x18008bb0c  mov     edx, edi
0x18008bb0e  lea     rcx, [rsp+0F8h+lpBuffer]; lpSrc
0x18008bb16  call    ?LaunchDtDumpOutOfProc@Os@Utils@Diagnostics@Microsoft@@CAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@8@_K@Z; Microsoft::Diagnostics::Utils::Os::LaunchDtDumpOutOfProc(std::wstring &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,unsigned __int64)
0x18008bb1b  mov     ebx, eax
0x18008bb1d  test    eax, eax
0x18008bb1f  jns     short loc_18008BB3E
0x18008bb21  mov     rcx, [rsp+0F8h]; this
0x18008bb29  mov     r9d, eax; char *
0x18008bb2c  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008bb33  mov     edx, 4E7h; void *
0x18008bb38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bb3d  nop
0x18008bb3e  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008bb46  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008bb4b  nop
0x18008bb4c  lea     rcx, [rsp+0F8h+var_B8]
0x18008bb51  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008bb56  mov     eax, ebx
0x18008bb58  jmp     loc_18008BCE7
0x18008bb5d  lea     rax, aDbghelpDll; "dbghelp.dll"
0x18008bb64  mov     [rsp+0F8h+var_88], rax
0x18008bb69  mov     [rsp+0F8h+var_80], 0Bh
0x18008bb72  lea     rdx, [rsp+0F8h+var_88]
0x18008bb77  lea     rcx, [rsp+0F8h+hModule]
0x18008bb7c  call    ?LoadSystemLibrary@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::LoadSystemLibrary(std::wstring_view)
0x18008bb81  nop
0x18008bb82  mov     rcx, [rsp+0F8h+hModule]; hModule
0x18008bb87  test    rcx, rcx
0x18008bb8a  jnz     short loc_18008BBD1
0x18008bb8c  mov     rcx, [rsp+0F8h]; this
0x18008bb94  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008bb9b  mov     edx, 4ECh; void *
0x18008bba0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008bba5  mov     ebx, eax
0x18008bba7  lea     rcx, [rsp+0F8h+hModule]
0x18008bbac  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18008bbb1  nop
0x18008bbb2  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008bbba  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008bbbf  nop
0x18008bbc0  lea     rcx, [rsp+0F8h+var_B8]
0x18008bbc5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008bbca  mov     eax, ebx
0x18008bbcc  jmp     loc_18008BCE7
0x18008bbd1  lea     rdx, aMinidumpwrited; "MiniDumpWriteDump"
0x18008bbd8  call    cs:__imp_GetProcAddress
0x18008bbdf  nop     dword ptr [rax+rax+00h]
0x18008bbe4  test    rax, rax
0x18008bbe7  jnz     short loc_18008BC2E
0x18008bbe9  mov     rcx, [rsp+0F8h]; this
0x18008bbf1  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x18008bbf8  mov     edx, 4F3h; void *
0x18008bbfd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008bc02  mov     ebx, eax
0x18008bc04  lea     rcx, [rsp+0F8h+hModule]
0x18008bc09  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18008bc0e  nop
0x18008bc0f  lea     rcx, [rsp+0F8h+lpBuffer]; this
0x18008bc17  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008bc1c  nop
0x18008bc1d  lea     rcx, [rsp+0F8h+var_B8]
0x18008bc22  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008bc27  mov     eax, ebx
0x18008bc29  jmp     loc_18008BCE7
0x18008bc2e  mov     [rsp+0F8h+var_AC], r15d
0x18008bc33  lea     rcx, ?MinidumpCallback@Os@Utils@Diagnostics@Microsoft@@CAHPEAXPEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; Microsoft::Diagnostics::Utils::Os::MinidumpCallback(void *,_MINIDUMP_CALLBACK_INPUT *,_MINIDUMP_CALLBACK_OUTPUT *)
0x18008bc3a  mov     [rsp+0F8h+var_58], rcx
0x18008bc42  lea     rcx, [rsp+0F8h+var_AC]
0x18008bc47  mov     [rsp+0F8h+var_50], rcx
0x18008bc4f  lea     rcx, [rsp+0F8h+var_58]
  ... truncated ...
```
