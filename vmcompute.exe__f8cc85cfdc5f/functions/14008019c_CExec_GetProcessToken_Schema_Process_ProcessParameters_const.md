# CExec::GetProcessToken(Schema::Process::ProcessParameters const &)

- ea: `0x14008019c`
- end: `0x140080697`
- name: `?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z`
- size: `1275`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140080ed8`

## callees

- `0x140017040`
- `0x140024030`
- `0x140031038`
- `0x1400421f0`
- `0x140042468`
- `0x140044974`
- `0x140080180`
- `0x14008019c`
- `0x140082f4c`
- `0x1400842c0`
- `0x1400ad53c`
- `0x1400c4154`
- `0x14010c340`
- `0x1401332f0`
- `0x140136a18`
- `0x140282530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080340`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008042b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080456`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008050a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080528`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080340`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008042b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080456`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008050a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140080528`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1400803e6`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1400803e6`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400804cb`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400804cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14008055b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14008055b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140080544`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140080544`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400805ae`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x14008060c`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1400805ae`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x14008060c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400803ba`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400803ba`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140080369`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140080369`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400802b1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x1400802b1`

## string_xrefs

- `0x140080266`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400802c5`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14008037d`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400803d5`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400804e3`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140080573`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400805c6`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140080624`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct _WTS_SESSION_INFO_1W *__fastcall CExec::GetProcessToken(struct _WTS_SESSION_INFO_1W *a1, __int64 a2)
{
  PWTS_SESSION_INFO_1W v4; // rbx
  const WCHAR *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r15
  __int64 v10; // rax
  const char *v11; // r9
  const unsigned __int16 *v12; // r8
  struct _WTS_SESSION_INFO_1W *v13; // r14
  CExec *pDomainName; // rcx
  const unsigned __int16 *v15; // rdx
  void **v16; // rax
  const char *v17; // r9
  __int64 v18; // rdx
  __int64 ContainerVirtualAccountToken; // rax
  void **NewTokenHandle; // rax
  const char *v21; // r9
  LPCWSTR *v22; // rcx
  void **v23; // rbx
  HANDLE CurrentProcess; // rax
  const char *v25; // r9
  void **v26; // rax
  const WCHAR *v27; // rdx
  const char *v28; // r9
  void **v29; // rax
  const char *v30; // r9
  unsigned int pCount; // [rsp+20h] [rbp-79h]
  unsigned int pCounta; // [rsp+20h] [rbp-79h]
  _QWORD v34[2]; // [rsp+58h] [rbp-41h] BYREF
  char v35; // [rsp+68h] [rbp-31h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+78h] [rbp-21h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+80h] [rbp-19h] BYREF
  DWORD NumberOfEntries; // [rsp+88h] [rbp-11h] BYREF
  DWORD pLevel; // [rsp+8Ch] [rbp-Dh] BYREF
  LPCWSTR lpszDomain[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v41; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]
  _QWORD v43[2]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  ppSessionInfo = a1;
  std::wstring::wstring(lpszDomain);
  v4 = (PWTS_SESSION_INFO_1W)(a2 + 88);
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v5 = (const WCHAR *)(a2 + 88);
  else
    v5 = *(const WCHAR **)&v4->ExecEnvId;
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v6 = a2 + 88;
  else
    v6 = *(_QWORD *)&v4->ExecEnvId;
  v7 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v6, *(_QWORD *)(a2 + 104), 0, 92);
  v9 = v7;
  if ( v7 != -1 )
  {
    v10 = std::wstring::substr(a2 + 88, v34, 0, v7);
    std::wstring::operator=(lpszDomain, v10);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v34);
    v5 += v9 + 1;
  }
  if ( *(_BYTE *)(a2 + 179) )
  {
    if ( !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4E1,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)0x32,
        pCount);
    ppSessionInfo = 0;
    NumberOfEntries = 0;
    v34[0] = &ppSessionInfo;
    v34[1] = &NumberOfEntries;
    v35 = 1;
    pLevel = 1;
    if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4EF,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v11);
    v4 = ppSessionInfo;
    gsl::details::extent_type<-1>::extent_type<-1>(v43, NumberOfEntries);
    if ( v43[0] != -1 && (v4 || !v43[0]) )
    {
      v13 = &v4[v43[0]];
      while ( 1 )
      {
        if ( v4 == v13 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x4FD,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
            (const char *)0x520,
            pCounta);
        pDomainName = (CExec *)v4->pDomainName;
        if ( pDomainName && v4->pUserName )
        {
          v15 = (const unsigned __int16 *)lpszDomain;
          if ( v42 > 7 )
            v15 = lpszDomain[0];
          if ( CExec::DomainMatchesSession(pDomainName, v15, v12) && !(unsigned int)_o__wcsicmp(v4->pUserName, v5) )
            break;
        }
        ++v4;
      }
      v43[0] = 0;
      v16 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(v43);
      if ( !WTSQueryUserToken(v4->SessionId, v16) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x4F8,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v17);
      *(_QWORD *)&a1->ExecEnvId = v43[0];
      v43[0] = 0;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v43);
      if ( ppSessionInfo )
        WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries);
      goto LABEL_60;
    }
    _o_terminate();
  }
  if ( !*(_QWORD *)(a2 + 104) )
  {
    LOBYTE(v8) = *(_BYTE *)(a2 + 168) == 0;
    CExec::MakeContainerVirtualAccountToken(a1, v8);
    goto LABEL_60;
  }
  ExistingTokenHandle = 0;
  if ( v41 )
    goto LABEL_44;
  if ( (unsigned int)_o__wcsicmp(v5, L"ContainerAdministrator") )
  {
    if ( !v41 && !(unsigned int)_o__wcsicmp(v5, L"ContainerUser") )
    {
      v18 = 0;
      goto LABEL_40;
    }
LABEL_44:
    v22 = lpszDomain;
    if ( v42 > 7 )
      v22 = (LPCWSTR *)lpszDomain[0];
    if ( (unsigned int)_o__wcsicmp(v22, L"NT AUTHORITY") )
    {
      v29 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&ExistingTokenHandle);
      if ( v4->pHostName > (LPWSTR)7 )
        v4 = *(PWTS_SESSION_INFO_1W *)&v4->ExecEnvId;
      if ( !LogonUserW((LPCWSTR)v4, L".", &szPassword, 2u, 0, v29) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x52B,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v30);
    }
    else if ( (unsigned int)_o__wcsicmp(v5, L"SYSTEM") )
    {
      v26 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&ExistingTokenHandle);
      v27 = (const WCHAR *)lpszDomain;
      if ( v42 > 7 )
        v27 = lpszDomain[0];
      if ( !LogonUserW(v5, v27, 0, 5u, 0, v26) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x51F,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v28);
    }
    else
    {
      v23 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&ExistingTokenHandle);
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, v23) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x515,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v25);
    }
    goto LABEL_41;
  }
  LOBYTE(v18) = 1;
LABEL_40:
  ContainerVirtualAccountToken = CExec::MakeContainerVirtualAccountToken(&ppSessionInfo, v18);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &ExistingTokenHandle,
    ContainerVirtualAccountToken);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ppSessionInfo);
LABEL_41:
  if ( *(_BYTE *)(a2 + 168) )
  {
    ppSessionInfo = 0;
    NewTokenHandle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&ppSessionInfo);
    if ( !CreateRestrictedToken(ExistingTokenHandle, 4u, 0, 0, 0, 0, 0, 0, NewTokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &ExistingTokenHandle,
      &ppSessionInfo);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ppSessionInfo);
  }
  *(_QWORD *)&a1->ExecEnvId = ExistingTokenHandle;
  ExistingTokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
LABEL_60:
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpszDomain);
  return a1;
}

```

## disassembly

```asm
0x14008019c  mov     [rsp-8+arg_10], rbx
0x1400801a1  mov     [rsp-8+arg_18], rsi
0x1400801a6  push    rbp
0x1400801a7  push    rdi
0x1400801a8  push    r12
0x1400801aa  push    r14
0x1400801ac  push    r15
0x1400801ae  lea     rbp, [rsp-37h]
0x1400801b3  sub     rsp, 0D0h
0x1400801ba  mov     rax, cs:__security_cookie
0x1400801c1  xor     rax, rsp
0x1400801c4  mov     [rbp+57h+var_30], rax
0x1400801c8  mov     r14, rdx
0x1400801cb  mov     rdi, rcx
0x1400801ce  mov     [rbp+57h+ppSessionInfo], rcx
0x1400801d2  xor     r12d, r12d
0x1400801d5  lea     rcx, [rbp+57h+lpszDomain]; void *
0x1400801d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400801de  nop
0x1400801df  lea     rbx, [r14+58h]
0x1400801e3  cmp     qword ptr [rbx+18h], 7
0x1400801e8  jbe     short loc_1400801EF
0x1400801ea  mov     rsi, [rbx]
0x1400801ed  jmp     short loc_1400801F2
0x1400801ef  mov     rsi, rbx
0x1400801f2  jbe     short loc_1400801F9
0x1400801f4  mov     rcx, [rbx]
0x1400801f7  jmp     short loc_1400801FC
0x1400801f9  mov     rcx, rbx
0x1400801fc  mov     r9d, 5Ch ; '\'
0x140080202  xor     r8d, r8d
0x140080205  mov     rdx, [rbx+10h]
0x140080209  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x14008020e  mov     r15, rax
0x140080211  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140080215  jz      short loc_140080246
0x140080217  mov     r9, rax
0x14008021a  xor     r8d, r8d
0x14008021d  lea     rdx, [rbp+57h+var_98]
0x140080221  mov     rcx, rbx
0x140080224  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x140080229  mov     rdx, rax
0x14008022c  lea     rcx, [rbp+57h+lpszDomain]
0x140080230  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140080235  lea     rcx, [rbp+57h+var_98]; this
0x140080239  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008023e  lea     rsi, [rsi+r15*2]
0x140080242  add     rsi, 2
0x140080246  cmp     [r14+0B3h], r12b
0x14008024d  jz      loc_1400803F3
0x140080253  call    IsWTSEnumerateSessionsExWPresent
0x140080258  test    al, al
0x14008025a  jnz     short loc_140080278
0x14008025c  mov     rcx, [rbp+5Fh]; this
0x140080260  mov     r9d, 32h ; '2'; char *
0x140080266  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14008026d  mov     edx, 4E1h; void *
0x140080272  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140080278  mov     [rbp+57h+ppSessionInfo], r12
0x14008027c  mov     [rbp+57h+NumberOfEntries], r12d
0x140080280  lea     rax, [rbp+57h+ppSessionInfo]
0x140080284  mov     [rbp+57h+var_98], rax
0x140080288  lea     rax, [rbp+57h+NumberOfEntries]
0x14008028c  mov     [rbp+57h+var_90], rax
0x140080290  mov     [rbp+57h+var_88], 1
0x140080294  mov     [rbp+57h+pLevel], 1
0x14008029b  lea     rax, [rbp+57h+NumberOfEntries]
0x14008029f  mov     [rsp+0F0h+pCount], rax; unsigned int
0x1400802a4  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x1400802a8  xor     r8d, r8d; Filter
0x1400802ab  lea     rdx, [rbp+57h+pLevel]; pLevel
0x1400802af  xor     ecx, ecx; hServer
0x1400802b1  call    cs:__imp_WTSEnumerateSessionsExW
0x1400802b8  nop     dword ptr [rax+rax+00h]
0x1400802bd  mov     rcx, [rbp+5Fh]; this
0x1400802c1  test    eax, eax
0x1400802c3  jnz     short loc_1400802D7
0x1400802c5  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400802cc  mov     edx, 4EFh; void *
0x1400802d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400802d7  mov     rbx, [rbp+57h+ppSessionInfo]
0x1400802db  mov     edx, [rbp+57h+NumberOfEntries]
0x1400802de  lea     rcx, [rbp+57h+var_40]
0x1400802e2  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x1400802e7  mov     rax, [rbp+57h+var_40]
0x1400802eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400802ef  jz      loc_1400803E6
0x1400802f5  test    rbx, rbx
0x1400802f8  jnz     short loc_140080303
0x1400802fa  test    rax, rax
0x1400802fd  jnz     loc_1400803E6
0x140080303  imul    r14, rax, 38h ; '8'
0x140080307  add     r14, rbx
0x14008030a  cmp     rbx, r14
0x14008030d  jz      loc_1400803CB
0x140080313  mov     rcx, [rbx+28h]; this
0x140080317  test    rcx, rcx
0x14008031a  jz      short loc_140080350
0x14008031c  cmp     [rbx+20h], r12
0x140080320  jz      short loc_140080350
0x140080322  lea     rdx, [rbp+57h+lpszDomain]
0x140080326  cmp     [rbp+57h+var_48], 7
0x14008032b  cmova   rdx, [rbp+57h+lpszDomain]; unsigned __int16 *
0x140080330  call    ?DomainMatchesSession@CExec@@YA_NPEBG0@Z; CExec::DomainMatchesSession(ushort const *,ushort const *)
0x140080335  test    al, al
0x140080337  jz      short loc_140080350
0x140080339  mov     rdx, rsi
0x14008033c  mov     rcx, [rbx+20h]
0x140080340  call    cs:__imp__o__wcsicmp
0x140080347  nop     dword ptr [rax+rax+00h]
0x14008034c  test    eax, eax
0x14008034e  jz      short loc_140080356
0x140080350  add     rbx, 38h ; '8'
0x140080354  jmp     short loc_14008030A
0x140080356  mov     [rbp+57h+var_40], r12
0x14008035a  lea     rcx, [rbp+57h+var_40]
0x14008035e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140080363  mov     rdx, rax; phToken
0x140080366  mov     ecx, [rbx+8]; SessionId
0x140080369  call    cs:__imp_WTSQueryUserToken
0x140080370  nop     dword ptr [rax+rax+00h]
0x140080375  mov     rcx, [rbp+5Fh]; this
0x140080379  test    eax, eax
0x14008037b  jnz     short loc_14008038F
0x14008037d  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140080384  mov     edx, 4F8h; void *
0x140080389  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14008038f  mov     rax, [rbp+57h+var_40]
0x140080393  mov     [rdi], rax
0x140080396  mov     [rbp+57h+var_40], r12
0x14008039a  lea     rcx, [rbp+57h+var_40]; void *
0x14008039e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400803a3  nop
0x1400803a4  mov     rdx, [rbp+57h+ppSessionInfo]; pMemory
0x1400803a8  test    rdx, rdx
0x1400803ab  jz      loc_140080662
0x1400803b1  mov     r8d, [rbp+57h+NumberOfEntries]; NumberOfEntries
0x1400803b5  mov     ecx, 2; WTSTypeClass
0x1400803ba  call    cs:__imp_WTSFreeMemoryExW
0x1400803c1  nop     dword ptr [rax+rax+00h]
0x1400803c6  jmp     loc_140080662
0x1400803cb  mov     rcx, [rbp+5Fh]; this
0x1400803cf  mov     r9d, 520h; char *
0x1400803d5  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400803dc  lea     edx, [r9-23h]; void *
0x1400803e0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400803e6  call    cs:__imp__o_terminate
0x1400803ed  nop     dword ptr [rax+rax+00h]
0x1400803f2  nop
0x1400803f3  cmp     [r14+68h], r12
0x1400803f7  jnz     short loc_140080410
0x1400803f9  cmp     [r14+0A8h], r12b
0x140080400  setz    dl
0x140080403  mov     rcx, rdi
0x140080406  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x14008040b  jmp     loc_140080662
0x140080410  mov     [rbp+57h+ExistingTokenHandle], r12
0x140080414  mov     rax, [rbp+57h+var_50]
0x140080418  test    rax, rax
0x14008041b  jnz     loc_1400804F5
0x140080421  lea     rdx, aContaineradmin; "ContainerAdministrator"
0x140080428  mov     rcx, rsi
0x14008042b  call    cs:__imp__o__wcsicmp
0x140080432  nop     dword ptr [rax+rax+00h]
0x140080437  test    eax, eax
0x140080439  jnz     short loc_14008043F
0x14008043b  mov     dl, 1
0x14008043d  jmp     short loc_14008046C
0x14008043f  mov     rax, [rbp+57h+var_50]
0x140080443  test    rax, rax
0x140080446  jnz     loc_1400804F5
0x14008044c  lea     rdx, aContaineruser; "ContainerUser"
0x140080453  mov     rcx, rsi
0x140080456  call    cs:__imp__o__wcsicmp
0x14008045d  nop     dword ptr [rax+rax+00h]
0x140080462  test    eax, eax
0x140080464  jnz     loc_1400804F5
0x14008046a  xor     edx, edx
0x14008046c  lea     rcx, [rbp+57h+ppSessionInfo]
0x140080470  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x140080475  mov     rdx, rax
0x140080478  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x14008047c  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140080481  lea     rcx, [rbp+57h+ppSessionInfo]; void *
0x140080485  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008048a  cmp     [r14+0A8h], r12b
0x140080491  jz      loc_14008064D
0x140080497  mov     [rbp+57h+ppSessionInfo], r12
0x14008049b  lea     rcx, [rbp+57h+ppSessionInfo]
0x14008049f  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1400804a4  mov     [rsp+0F0h+NewTokenHandle], rax; NewTokenHandle
0x1400804a9  mov     [rsp+0F0h+SidsToRestrict], r12; SidsToRestrict
0x1400804ae  mov     [rsp+0F0h+RestrictedSidCount], r12d; RestrictedSidCount
0x1400804b3  mov     [rsp+0F0h+PrivilegesToDelete], r12; PrivilegesToDelete
0x1400804b8  mov     dword ptr [rsp+0F0h+pCount], r12d; DeletePrivilegeCount
0x1400804bd  xor     r9d, r9d; SidsToDisable
0x1400804c0  xor     r8d, r8d; DisableSidCount
0x1400804c3  lea     edx, [r9+4]; Flags
0x1400804c7  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x1400804cb  call    cs:__imp_CreateRestrictedToken
0x1400804d2  nop     dword ptr [rax+rax+00h]
0x1400804d7  mov     rcx, [rbp+5Fh]; this
0x1400804db  test    eax, eax
0x1400804dd  jnz     loc_140080636
0x1400804e3  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400804ea  mov     edx, 53Bh; void *
0x1400804ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400804f5  lea     rcx, [rbp+57h+lpszDomain]
0x1400804f9  cmp     [rbp+57h+var_48], 7
0x1400804fe  cmova   rcx, [rbp+57h+lpszDomain]
0x140080503  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x14008050a  call    cs:__imp__o__wcsicmp
0x140080511  nop     dword ptr [rax+rax+00h]
0x140080516  test    eax, eax
0x140080518  jnz     loc_1400805D8
0x14008051e  lea     rdx, aSystem_0; "SYSTEM"
0x140080525  mov     rcx, rsi
0x140080528  call    cs:__imp__o__wcsicmp
0x14008052f  nop     dword ptr [rax+rax+00h]
0x140080534  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x140080538  test    eax, eax
0x14008053a  jnz     short loc_140080585
0x14008053c  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140080541  mov     rbx, rax
0x140080544  call    cs:__imp_GetCurrentProcess
0x14008054b  nop     dword ptr [rax+rax+00h]
0x140080550  mov     r8, rbx; TokenHandle
0x140080553  mov     edx, 0F01FFh; DesiredAccess
0x140080558  mov     rcx, rax; ProcessHandle
0x14008055b  call    cs:__imp_OpenProcessToken
0x140080562  nop     dword ptr [rax+rax+00h]
0x140080567  mov     rcx, [rbp+5Fh]; this
0x14008056b  test    eax, eax
0x14008056d  jnz     loc_14008048A
0x140080573  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14008057a  mov     edx, 515h; void *
0x14008057f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140080585  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x14008058a  lea     rdx, [rbp+57h+lpszDomain]
0x14008058e  cmp     [rbp+57h+var_48], 7
0x140080593  cmova   rdx, [rbp+57h+lpszDomain]; lpszDomain
0x140080598  mov     [rsp+0F0h+PrivilegesToDelete], rax; phToken
0x14008059d  mov     dword ptr [rsp+0F0h+pCount], r12d; dwLogonProvider
0x1400805a2  mov     r9d, 5; dwLogonType
0x1400805a8  xor     r8d, r8d; lpszPassword
0x1400805ab  mov     rcx, rsi; lpszUsername
0x1400805ae  call    cs:__imp_LogonUserW
0x1400805b5  nop     dword ptr [rax+rax+00h]
0x1400805ba  mov     rcx, [rbp+5Fh]; this
0x1400805be  test    eax, eax
0x1400805c0  jnz     loc_14008048A
0x1400805c6  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400805cd  mov     edx, 51Fh; void *
0x1400805d2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400805d8  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x1400805dc  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1400805e1  cmp     qword ptr [rbx+18h], 7
0x1400805e6  jbe     short loc_1400805EB
0x1400805e8  mov     rbx, [rbx]
0x1400805eb  mov     [rsp+0F0h+PrivilegesToDelete], rax; phToken
0x1400805f0  mov     dword ptr [rsp+0F0h+pCount], r12d; dwLogonProvider
0x1400805f5  mov     r9d, 2; dwLogonType
0x1400805fb  lea     r8, szPassword; lpszPassword
0x140080602  lea     rdx, szDomain; "."
0x140080609  mov     rcx, rbx; lpszUsername
0x14008060c  call    cs:__imp_LogonUserW
0x140080613  nop     dword ptr [rax+rax+00h]
0x140080618  mov     rcx, [rbp+5Fh]; this
0x14008061c  test    eax, eax
0x14008061e  jnz     loc_14008048A
0x140080624  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14008062b  mov     edx, 52Bh; void *
0x140080630  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140080636  lea     rdx, [rbp+57h+ppSessionInfo]
0x14008063a  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x14008063e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140080643  nop
0x140080644  lea     rcx, [rbp+57h+ppSessionInfo]; void *
0x140080648  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14008064d  mov     rax, [rbp+57h+ExistingTokenHandle]
0x140080651  mov     [rdi], rax
0x140080654  mov     [rbp+57h+ExistingTokenHandle], r12
0x140080658  lea     rcx, [rbp+57h+ExistingTokenHandle]; void *
0x14008065c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140080661  nop
0x140080662  lea     rcx, [rbp+57h+lpszDomain]; this
0x140080666  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008066b  mov     rax, rdi
0x14008066e  mov     rcx, [rbp+57h+var_30]
0x140080672  xor     rcx, rsp; StackCookie
0x140080675  call    __security_check_cookie
0x14008067a  lea     r11, [rsp+0F0h+var_20]
0x140080682  mov     rbx, [r11+40h]
0x140080686  mov     rsi, [r11+48h]
0x14008068a  mov     rsp, r11
0x14008068d  pop     r15
0x14008068f  pop     r14
0x140080691  pop     r12
0x140080693  pop     rdi
0x140080694  pop     rbp
  ... truncated ...
```
